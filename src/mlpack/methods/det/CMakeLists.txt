# Define the files we need to compile
# Anything not in this list will not be compiled into the output library
# Do not include test programs here
set(SOURCES
  # the DET class
  dtree.hpp
  dtree_impl.hpp

  # Utility files
  dt_utils.hpp
  dt_utils_impl.hpp
)

# add directory name to sources
set(DIR_SRCS)
foreach(file ${SOURCES})
  set(DIR_SRCS ${DIR_SRCS} ${CMAKE_CURRENT_SOURCE_DIR}/${file})
endforeach()
# append sources (with directory name) to list of all mlpack sources (used at the parent scope)
set(MLPACK_SRCS ${MLPACK_SRCS} ${DIR_SRCS} PARENT_SCOPE)

add_category(det "misc. / other")
add_cli_executable(det)
add_python_binding(det)
add_julia_binding(det)
add_go_binding(det)
add_r_binding(det)
add_markdown_docs(det "cli;python;julia;go;r" "")
