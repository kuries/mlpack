# Define the files we need to compile.
# Anything not in this list will not be compiled into mlpack.
set(SOURCES
  range_search.hpp
  range_search_impl.hpp
  range_search_rules.hpp
  range_search_rules_impl.hpp
  range_search_stat.hpp
  rs_model.hpp
  rs_model_impl.hpp
  rs_model.cpp
)

# Add directory name to sources.
set(DIR_SRCS)
foreach(file ${SOURCES})
  set(DIR_SRCS ${DIR_SRCS} ${CMAKE_CURRENT_SOURCE_DIR}/${file})
endforeach()
# Append sources (with directory name) to list of all mlpack sources (used at
# the parent scope).
set(MLPACK_SRCS ${MLPACK_SRCS} ${DIR_SRCS} PARENT_SCOPE)

add_category(range_search "geometry")
add_cli_executable(range_search)
#add_python_binding(range_search)
#add_julia_binding(range_search)
#add_go_binding(range_search)
#add_r_binding(range_search)
add_markdown_docs(range_search "cli" "")
