set(name main-simple)
set(source_files ${name}.cc)
set(header_files)
set(libraries_to_link ${libnetwork} ${libinternet} ${libapplications})
set(files_to_copy)
build_lib_example ("${name}" "${source_files}" "${header_files}" "${libraries_to_link}" "${files_to_copy}")


