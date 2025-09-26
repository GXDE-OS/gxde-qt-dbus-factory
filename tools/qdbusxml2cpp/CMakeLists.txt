qt_add_executable(qdbusxml2cpp-fix WIN32 MACOSX_BUNDLE
    qdbusxml2cpp.cpp
)
target_link_libraries(qdbusxml2cpp-fix PRIVATE
    Qt::Core
    Qt::DBusPrivate
    Qt::Gui
)

if(host_sw_64)
    target_compile_options(qdbusxml2cpp-fix
        -mieee
    )
endif()

install(TARGETS qdbusxml2cpp-fix
    BUNDLE DESTINATION .
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)

# Consider using qt_generate_deploy_app_script() for app deployment if
# the project can use Qt 6.3. In that case rerun qmake2cmake with
# --min-qt-version=6.3.
