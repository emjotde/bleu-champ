

add_executable(bleu-champ bleu-champ.cpp $<TARGET_OBJECTS:util>)

target_link_libraries(bleu-champ ${EXT_LIBS})

set_target_properties(bleu-champ
    PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
