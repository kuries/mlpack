# Define the files we need to compile.
# Anything not in this list will not be compiled into mlpack.
set(SOURCES
  # DrusillaSelect sources.
  drusilla_select.hpp
  drusilla_select_impl.hpp
  # QDAFN sources.
  qdafn.hpp
  qdafn_impl.hpp
)

# Add directory name to sources.
set(DIR_SRCS)
foreach(file ${SOURCES})
  set(DIR_SRCS ${DIR_SRCS} ${CMAKE_CURRENT_SOURCE_DIR}/${file})
endforeach()
# Append sources (with directory name) to list of all mlpack sources (used at
# the parent scope).
set(MLPACK_SRCS ${MLPACK_SRCS} ${DIR_SRCS} PARENT_SCOPE)

# This program computes approximate furthest neighbors.
add_category(approx_kfn "geometry")
add_cli_executable(approx_kfn)
add_python_binding(approx_kfn)
add_julia_binding(approx_kfn)
add_go_binding(approx_kfn)
add_r_binding(approx_kfn)
add_markdown_docs(approx_kfn "cli;python;julia;go;r" "")
