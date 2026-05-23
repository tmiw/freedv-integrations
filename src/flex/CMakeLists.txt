add_executable(freedv-flex
    main.cpp 
    FlexKeyValueParser.cpp 
    FlexVitaTask.cpp
    FlexTcpTask.cpp)

target_compile_options(freedv-flex PRIVATE ${WARNINGS_AS_ERRORS_FLAGS} -Wno-missing-field-initializers)
target_link_libraries(freedv-flex PRIVATE git_version fdv_audio_pipeline fdv_reporting fdv_util fdv_integ_common r8brain)

# If on Linux, force static libstdc++. This is to prevent versioning
# problems when using AppImages.
if(LINUX AND STATIC_LIBGCC)
    target_link_options(freedv-flex PRIVATE -static-libgcc -static-libstdc++)
endif(LINUX AND STATIC_LIBGCC)
