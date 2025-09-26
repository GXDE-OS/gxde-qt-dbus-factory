qt_add_library(dframeworkdbus
    qtdbusextended/DBusExtended
    qtdbusextended/DBusExtendedAbstractInterface
    qtdbusextended/dbusextended.h
    qtdbusextended/dbusextendedabstractinterface.cpp qtdbusextended/dbusextendedabstractinterface.h
    qtdbusextended/dbusextendedpendingcallwatcher.cpp qtdbusextended/dbusextendedpendingcallwatcher_p.h
    types/appscgroupinfo.h
    types/appscgroupinfolist.cpp types/appscgroupinfolist.h
    types/appupdateinfolist.cpp types/appupdateinfolist.h
    types/arealist.cpp types/arealist.h
    types/arrayint.cpp types/arrayint.h
    types/audioport.cpp types/audioport.h
    types/audioportlist.cpp types/audioportlist.h
    types/batterypercentageinfo.cpp types/batterypercentageinfo.h
    types/batterypresentinfo.cpp types/batterypresentinfo.h
    types/batterystateinfo.cpp types/batterystateinfo.h
    types/brightnessmap.cpp types/brightnessmap.h
    types/chrometablist.cpp types/chrometablist.h
    types/controlcenterrect.cpp types/controlcenterrect.h
    types/dbusimagelist.cpp types/dbusimagelist.h
    types/dbusobjectpathlist.cpp types/dbusobjectpathlist.h
    types/dbustooltip.cpp types/dbustooltip.h
    types/defenderappflow.cpp types/defenderappflow.h
    types/defenderdisplay.cpp types/defenderdisplay.h
    types/defenderdissection.cpp types/defenderdissection.h
    types/defenderfileinfo.cpp types/defenderfileinfo.h
    types/defenderprocessinfo.cpp types/defenderprocessinfo.h
    types/defenderprocesslist.cpp types/defenderprocesslist.h
    types/defenderprocinfo.cpp types/defenderprocinfo.h
    types/defenderprocinfolist.cpp types/defenderprocinfolist.h
    types/defenderupdatestate.cpp types/defenderupdatestate.h
    types/defenderversioninfo.cpp types/defenderversioninfo.h
    types/dockrect.cpp types/dockrect.h
    types/hardwareinfo.cpp types/hardwareinfo.h
    types/inputdevicelist.cpp types/inputdevicelist.h
    types/intstring.cpp types/intstring.h
    types/keyboardlayoutlist.cpp types/keyboardlayoutlist.h
    types/lastoreupdatepackagesinfo.cpp types/lastoreupdatepackagesinfo.h
    types/launcheriteminfo.cpp types/launcheriteminfo.h
    types/launcheriteminfolist.cpp types/launcheriteminfolist.h
    types/linkinfolist.cpp types/linkinfolist.h
    types/localelist.cpp types/localelist.h
    types/mfainfolist.cpp types/mfainfolist.h
    types/mirrorinfolist.cpp types/mirrorinfolist.h
    types/networkavailablekeys.cpp types/networkavailablekeys.h
    types/networkconnectiondata.cpp types/networkconnectiondata.h
    types/networkerrors.cpp types/networkerrors.h
    types/policydetails.cpp types/policydetails.h
    types/policyresult.cpp types/policyresult.h
    types/policysubject.cpp types/policysubject.h
    types/propertylist.cpp types/propertylist.h
    types/qvariantlist.cpp types/qvariantlist.h
    types/qvariantmap.cpp types/qvariantmap.h
    types/reflectlist.cpp types/reflectlist.h
    types/resolution.cpp types/resolution.h
    types/resolutionlist.cpp types/resolutionlist.h
    types/rotationlist.cpp types/rotationlist.h
    types/screenrect.cpp types/screenrect.h
    types/searchmap.cpp types/searchmap.h
    types/sinkinfolist.cpp types/sinkinfolist.h
    types/touchscreeninfolist.cpp types/touchscreeninfolist.h
    types/touchscreeninfolist_v2.cpp types/touchscreeninfolist_v2.h
    types/touchscreenmap.cpp types/touchscreenmap.h
    types/wacomdevicelist.cpp types/wacomdevicelist.h
    types/windowinfomap.cpp types/windowinfomap.h
    types/windowlist.cpp types/windowlist.h
    types/zoneinfo.cpp types/zoneinfo.h
)
target_include_directories(dframeworkdbus PUBLIC
    qtdbusextended
)

target_compile_definitions(dframeworkdbus PUBLIC
    _FORTITY_SOURCE=1
)

target_link_libraries(dframeworkdbus PUBLIC
    Qt::Core
    Qt::DBus
    Qt::Gui
)

target_compile_options(dframeworkdbus PUBLIC
    -fPIC
    -fstack-protector-strong
    -pie
    -z -z
    lazy
#    noexecstack
)

if(host_sw_64)
    target_compile_options(dframeworkdbus PUBLIC
        -mieee
    )
endif()

install(TARGETS dframeworkdbus
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    FRAMEWORK DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)
