
file(GLOB_RECURSE QML_SRCS *.qml *.js *.json)

set(calculator_SRCS
    main.cpp
    button.cpp
    calculator.cpp
    ${QML_SRCS}
)

add_executable(utouch-calculator ${calculator_SRCS})

qt5_use_modules(utouch-calculator Gui Widgets)
target_link_libraries(utouch-calculator stdc++)

if(CLICK_MODE)
  install(TARGETS utouch-calculator DESTINATION ${CMAKE_INSTALL_PREFIX})
else()
  install(TARGETS utouch-calculator RUNTIME DESTINATION ${CMAKE_INSTALL_PREFIX})
endif()
