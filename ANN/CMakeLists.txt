add_library(ann
    ANN.cpp
    ANN.h
    ANNperf.h
    ANNx.h
    bd_fix_rad_search.cpp
    bd_pr_search.cpp
    bd_search.cpp
    bd_tree.cpp
    bd_tree.h
    brute.cpp
    kd_dump.cpp
    kd_fix_rad_search.cpp
    kd_fix_rad_search.h
    kd_pr_search.cpp
    kd_pr_search.h
    kd_search.cpp
    kd_search.h
    kd_split.cpp
    kd_split.h
    kd_tree.cpp
    kd_tree.h
    kd_util.cpp
    kd_util.h
    perf.cpp
    pr_queue.h
    pr_queue_k.h
)

install(TARGETS ann 
EXPORT ann_export
LIBRARY ARCHIVE DESTINATION lib
INCLUDES DESTINATION include 
)
install(DIRECTORY "" DESTINATION include/ann FILES_MATCHING PATTERN "ANN*.h")

if("${CMAKE_SYSTEM_NAME}" MATCHES "Windows")
    install(FILES "${PROJECT_BINARY_DIR}/ann/CMakeFiles/ann.dir/ann.pdb" CONFIGURATIONS Debug DESTINATION lib)
endif()

install(EXPORT ann_export
FILE ann-config.cmake
DESTINATION cmake
EXPORT_LINK_INTERFACE_LIBRARIES
)