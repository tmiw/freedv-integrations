add_library(fdv_integ_common STATIC 
    ReportingController.cpp)

target_link_libraries(fdv_integ_common PRIVATE
    fdv_util
    fdv_reporting
    git_version)
