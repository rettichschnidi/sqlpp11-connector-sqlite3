#Add headers to IDE projects
file(GLOB_RECURSE HEADER_LIST ../include/*.h)

add_library(sqlpp11-connector-sqlite3
		connection.cpp
		bind_result.cpp
		prepared_statement.cpp
		detail/connection_handle.cpp
		${HEADER_LIST})

target_include_directories(sqlpp11-connector-sqlite3 PUBLIC ../include)
target_link_libraries(sqlpp11-connector-sqlite3 sqlpp11)

install(TARGETS sqlpp11-connector-sqlite3 DESTINATION lib)
