add_definitions(-DNGINTERFACE_EXPORTS)
add_library(interface ${NG_LIB_TYPE}
        nginterface.cpp nginterface_v2.cpp 
        read_fnf_mesh.cpp readtetmesh.cpp readuser.cpp writeabaqus.cpp writediffpack.cpp 
        writedolfin.cpp writeelmer.cpp writefeap.cpp writefluent.cpp writegmsh.cpp writejcm.cpp 
        writepermas.cpp writetecplot.cpp writetet.cpp writetochnog.cpp writeuser.cpp
        wuchemnitz.cpp writegmsh2.cpp writeOpenFOAM15x.cpp 
        )

target_link_libraries(interface mesh csg geom2d stl visual)

if(NOT WIN32)
  install( TARGETS interface ${NG_INSTALL_DIR})
endif(NOT WIN32)

install(FILES
  writeuser.hpp
  DESTINATION ${NG_INSTALL_DIR_INCLUDE}/interface COMPONENT netgen_devel
)
