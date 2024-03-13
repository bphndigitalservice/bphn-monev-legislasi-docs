classDiagram
direction BT
class app_configs {
   varchar(191) GROUP
   varchar(191) KEY
   varchar(191) VALUES
   tinyint(4) ENABLED
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class dashboard_target_view_rperpres_handed {
   int(1) not_ok
   int(1) ok
   int(1) super_ok
}
class dashboard_target_view_rperpres_new {
   int(1) not_ok
   int(1) ok
   int(1) super_ok
}
class dashboard_target_view_rpp_handed {
   int(1) not_ok
   int(1) ok
   int(1) super_ok
}
class dashboard_target_view_rpp_new {
   int(1) not_ok
   int(1) ok
   int(1) super_ok
}
class dashboard_target_view_ruu {
   int(1) not_ok
   int(1) ok
   int(1) super_ok
}
class dashboard_total_by_regtype {
   decimal(22) RUU
   decimal(22) RPP
   decimal(22) RPerpres
}
class dashboard_total_by_type {
   decimal(22) RPP_Baru
   decimal(22) RPP_Luncuran
   decimal(22) RPerpres_BARU
   decimal(22) RPerpres_Luncuran
}
class departments {
   varchar(191) uuid
   varchar(191) label
   varchar(191) desc
   timestamp created_at
   timestamp updated_at
   timestamp deleted_at
   bigint(20) unsigned id
}
class draft_count_groups {
   decimal(22) RUU
   decimal(22) RPP
   decimal(22) RPerpres
   year(4) year
}
class failed_jobs {
   varchar(191) uuid
   text connection
   text queue
   longtext payload
   longtext exception
   timestamp failed_at
   bigint(20) unsigned id
}
class imports {
   varchar(191) filename
   varchar(191) import_status
   longtext json_content
   tinyint(4) activity_count
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class initiatives {
   varchar(191) name
   varchar(191) description
   timestamp created_at
   timestamp updated_at
   timestamp deleted_at
   bigint(20) unsigned id
}
class local_to_minio_migrations {
   bigint(20) unsigned artifact_id
   enum('success', 'failed') migration_status
   varchar(255) info
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class long_term_task_histories {
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class migrations {
   varchar(191) migration
   int(11) batch
   int(10) unsigned id
}
class model_has_permissions {
   bigint(20) unsigned permission_id
   varchar(191) model_type
   bigint(20) unsigned model_id
}
class model_has_roles {
   bigint(20) unsigned role_id
   varchar(191) model_type
   bigint(20) unsigned model_id
}
class overall_monitoring_report {
   int(1) id
   int(1) program_id
   int(1) type
   int(1) label
   int(1) department
   int(1) program_task_id
   int(1) B03
   int(1) B06
   int(1) B09
   int(1) B12
}
class password_resets {
   varchar(191) email
   varchar(191) token
   timestamp created_at
}
class performance_calculation_details {
   bigint(20) unsigned performance_calculation_id
   bigint(20) unsigned program_task_id
   bigint(20) unsigned current_stage_id
   double default_weight
   double adjusted_weight
   timestamp created_at
   timestamp updated_at
   timestamp deleted_at
   bigint(20) unsigned id
}
class performance_calculation_results {
   bigint(20) unsigned performance_calculation_id
   int(11) total_subjects
   double total_weighted
   double total_adjusted_weight
   timestamp created_at
   timestamp updated_at
   timestamp deleted_at
   bigint(20) unsigned id
}
class performance_calculations {
   varchar(10) performance_calculation_period
   bigint(20) unsigned program_type_id
   bigint(20) unsigned department_id
   timestamp created_at
   timestamp updated_at
   timestamp deleted_at
   bigint(20) unsigned id
}
class performance_ranges {
   bigint(20) unsigned program_type_id
   double min_value
   double max_value
   varchar(191) label
   varchar(191) color
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class permissions {
   varchar(191) name
   varchar(191) guard_name
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class personal_access_tokens {
   varchar(191) tokenable_type
   bigint(20) unsigned tokenable_id
   varchar(191) name
   varchar(64) token
   text abilities
   timestamp last_used_at
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class program_target_artifact_definitions {
   varchar(191) target_period
   varchar(191) restrictions
   varchar(191) artifact_definition
   varchar(191) is_optional
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class program_target_artifact_defspecs {
   varchar(191) type
   varchar(191) program_spec
   varchar(191) artifact_defspec
   text override_desc
   tinyint(4) is_optional
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class program_target_artifact_specs {
   varchar(191) desc
   timestamp created_at
   timestamp updated_at
   varchar(191) spec
}
class program_target_definitions {
   text target_definition
   text restrictions
   text target_description
   timestamp created_at
   timestamp updated_at
   timestamp deleted_at
   enum('b03', 'b06', 'b09', 'b12') target_period
   varchar(191) target_measurement_unit
   bigint(20) unsigned task_stage_target_id
   tinyint(4) enabled
   bigint(20) unsigned id
}
class program_task_stages {
   int(11) type
   varchar(191) name
   varchar(255) slug
   varchar(191) desc
   timestamp created_at
   timestamp updated_at
   timestamp deleted_at
   int(11) weight
   bigint(20) unsigned id
}
class program_task_target_artifacts {
   bigint(20) unsigned program_task_id
   bigint(20) unsigned program_task_target_id
   bigint(20) unsigned user_id
   longtext path
   bigint(20) unsigned artifact_defspec_id
   varchar(191) attribute_1
   varchar(191) attribute_2
   varchar(191) attribute_3
   tinyint(4) is_optional
   tinyint(4) is_system
   varchar(191) uploaded_at
   timestamp created_at
   timestamp updated_at
   timestamp deleted_at
   tinyint(1) is_published
   bigint(20) unsigned id
}
class program_task_target_comments {
   bigint(20) unsigned program_task_target_id
   bigint(20) unsigned user_id
   text comment
   varchar(191) attribute_1
   varchar(191) attribute_2
   varchar(191) attribute_3
   timestamp created_at
   timestamp updated_at
   timestamp deleted_at
   bigint(20) unsigned id
}
class program_task_target_histories {
   bigint(20) unsigned reference_id
   bigint(20) unsigned program_task_id
   varchar(191) attribute_1
   varchar(191) attribute_2
   varchar(191) attribute_3
   timestamp created_at
   timestamp updated_at
   timestamp deleted_at
   text target_realization_description
   tinyint(4) is_approved
   bigint(20) unsigned target_definition_id
   bigint(20) unsigned task_stage_realization_id
   varchar(191) bottleneck_desc
   varchar(191) whatve_done
   tinyint(4) is_reporting
   double weight_adjustment
   bigint(20) unsigned id
}
class program_task_target_templates {
   varchar(191) restrictions
   enum('b03', 'b06', 'b09', 'b12') target_period
   text target_definition
   text target_description
   varchar(191) target_measurement_unit
   varchar(191) attribute_1
   varchar(191) attribute_2
   varchar(191) attribute_3
   timestamp deleted_at
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class program_task_targets {
   bigint(20) unsigned program_task_id
   varchar(191) attribute_1
   varchar(191) attribute_2
   varchar(191) attribute_3
   timestamp deleted_at
   timestamp created_at
   timestamp updated_at
   text target_realization_description
   tinyint(4) is_approved
   bigint(20) unsigned target_definition_id
   bigint(20) unsigned task_stage_realization_id
   varchar(255) bottleneck_desc
   varchar(255) whatve_done
   tinyint(4) is_reporting
   double weight_adjustment
   bigint(20) unsigned id
}
class program_task_types {
   varchar(191) uuid
   varchar(191) key
   varchar(191) label
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class program_tasks {
   varchar(191) uuid
   bigint(20) unsigned program_id
   bigint(20) unsigned department_id
   bigint(20) unsigned regulation_id
   enum('new', 'handed-down') type
   timestamp deleted_at
   timestamp created_at
   timestamp updated_at
   tinyint(4) is_handed_down
   bigint(20) unsigned stage_id
   tinyint(4) realization_value
   varchar(191) sirenkum_id
   varchar(255) extended_attribute_1
   varchar(255) extended_attribute_2
   varchar(255) extended_attribute_3
   varchar(255) extended_attribute_4
   varchar(255) extended_attribute_5
   tinyint(4) is_reportable
   tinyint(1) acknowledged
   bigint(20) unsigned id
}
class program_types {
   varchar(191) uuid
   varchar(191) type
   varchar(191) label
   text desc
   timestamp deleted_at
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class programs {
   varchar(191) uuid
   bigint(20) unsigned program_type_id
   varchar(191) label
   year(4) year
   text desc
   timestamp deleted_at
   timestamp created_at
   timestamp updated_at
   varchar(191) attribute_1
   varchar(191) attribute_2
   varchar(191) attribute_3
   varchar(191) attribute_4
   varchar(191) attribute_5
   bigint(20) unsigned id
}
class progress_report_view {
   bigint(20) unsigned id
   enum('new', 'handed-down') type
   text title
   varchar(191) stage
   varchar(191) department
   bigint(20) unsigned program_id
}
class regulation_histories {
   bigint(20) unsigned regulation_id
   varchar(191) uuid
   bigint(20) unsigned department_id
   enum('rpp', 'ruu', 'rperpres') type
   varchar(191) initiative_id
   text label
   text material
   text note
   varchar(191) attribute_1
   varchar(191) attribute_2
   varchar(191) attribute_3
   bigint(20) unsigned program_task_id
   timestamp deleted_at
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned stage_id
   bigint(20) unsigned id
}
class regulations {
   varchar(191) uuid
   bigint(20) unsigned department_id
   enum('ruu', 'rpp', 'rperpres') type
   varchar(191) initiative_id
   text label
   text material
   text note
   varchar(191) attribute_1
   varchar(191) attribute_2
   varchar(191) attribute_3
   timestamp deleted_at
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned stage_id
   bigint(20) unsigned id
}
class role_has_permissions {
   bigint(20) unsigned permission_id
   bigint(20) unsigned role_id
}
class roles {
   varchar(191) name
   varchar(191) guard_name
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class sessions {
   bigint(20) unsigned user_id
   varchar(45) ip_address
   text user_agent
   text payload
   int(11) last_activity
   varchar(191) id
}
class target_revision_acts {
   bigint(20) unsigned task_target_id
   bigint(20) unsigned user_id
   varchar(191) request_type
   varchar(191) request_comment
   varchar(191) extended_attribute_1
   varchar(191) extended_attribute_2
   varchar(191) extended_attribute_3
   tinyint(4) request_status
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned id
}
class users {
   varchar(191) name
   varchar(191) username
   varchar(191) email
   timestamp email_verified_at
   varchar(191) password
   text two_factor_secret
   text two_factor_recovery_codes
   varchar(100) remember_token
   varchar(191) current_team_id
   text profile_photo_path
   timestamp created_at
   timestamp updated_at
   bigint(20) unsigned department_id
   timestamp deleted_at
   bigint(20) unsigned id
}

model_has_permissions  -->  permissions : permission_id:id
model_has_roles  -->  roles : role_id:id
overall_monitoring_report  -->  program_tasks : program_task_id:id
overall_monitoring_report  -->  programs : program_id:id
performance_calculation_details  -->  performance_calculations : performance_calculation_id:id
performance_calculation_details  -->  program_tasks : program_task_id:id
performance_calculation_results  -->  performance_calculations : performance_calculation_id:id
performance_calculations  -->  departments : department_id:id
performance_calculations  -->  program_types : program_type_id:id
performance_ranges  -->  program_types : program_type_id:id
program_task_target_artifacts  -->  program_task_targets : program_task_target_id:id
program_task_target_artifacts  -->  program_tasks : program_task_id:id
program_task_target_artifacts  -->  users : user_id:id
program_task_target_comments  -->  program_task_targets : program_task_target_id:id
program_task_target_comments  -->  users : user_id:id
program_task_target_histories  -->  program_tasks : program_task_id:id
program_task_targets  -->  program_tasks : program_task_id:id
program_tasks  -->  departments : department_id:id
program_tasks  -->  programs : program_id:id
program_tasks  -->  regulations : regulation_id:id
programs  -->  program_types : program_type_id:id
progress_report_view  -->  programs : program_id:id
regulation_histories  -->  departments : department_id:id
regulation_histories  -->  initiatives : initiative_id:id
regulation_histories  -->  program_tasks : program_task_id:id
regulation_histories  -->  regulations : regulation_id:id
regulations  -->  departments : department_id:id
regulations  -->  initiatives : initiative_id:id
role_has_permissions  -->  permissions : permission_id:id
role_has_permissions  -->  roles : role_id:id
sessions  -->  users : user_id:id
target_revision_acts  -->  users : user_id:id
users  -->  departments : department_id:id
