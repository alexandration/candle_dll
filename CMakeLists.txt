cmake_minimum_required(VERSION 3.10)

add_library(candle_api SHARED
	candle.c
	candle_ctrl_req.c
)

target_compile_definitions(candle_api PRIVATE -DCANDLE_API_LIBRARY -DUNICODE)

target_link_libraries(candle_api PRIVATE
	setupapi
	winusb
	ole32
)

get_target_property(CANDLE_FILE candle_api CANDLE_OUTPUT_NAME)
