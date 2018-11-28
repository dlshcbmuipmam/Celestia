set(CELENGINE_SOURCES
  asterism.cpp
  asterism.h
  astro.cpp
  astro.h
  atmosphere.h
  axisarrow.cpp
  axisarrow.h
  body.cpp
  body.h
  boundaries.cpp
  boundaries.h
  catalogxref.cpp
  catalogxref.h
  celestia.h
  cmdparser.cpp
  cmdparser.h
  command.cpp
  command.h
  console.cpp
  console.h
  constellation.cpp
  constellation.h
  curveplot.cpp
  curveplot.h
  dds.cpp
  deepskyobj.cpp
  deepskyobj.h
  dispmap.cpp
  dispmap.h
  dsodb.cpp
  dsodb.h
  dsoname.cpp
  dsoname.h
  dsooctree.cpp
  dsooctree.h
  execenv.h
  execution.cpp
  execution.h
  frame.cpp
  frame.h
  frametree.cpp
  frametree.h
  galaxy.cpp
  galaxy.h
  geometry.h
  glcontext.cpp
  glcontext.h
  globular.cpp
  globular.h
  glshader.cpp
  glshader.h
  image.cpp
  image.h
  lightenv.h
  location.cpp
  location.h
  lodspheremesh.cpp
  lodspheremesh.h
  marker.cpp
  marker.h
  meshmanager.cpp
  meshmanager.h
  modelgeometry.cpp
  modelgeometry.h
  multitexture.cpp
  multitexture.h
  name.h
  nebula.cpp
  nebula.h
  observer.cpp
  observer.h
  octree.h
  opencluster.cpp
  opencluster.h
  overlay.cpp
  overlay.h
  parseobject.cpp
  parseobject.h
  parser.cpp
  parser.h
#  particlesystem.cpp
#  particlesystemfile.cpp
#  particlesystemfile.h
#  particlesystem.h
  planetgrid.cpp
  planetgrid.h
  referencemark.h
  rendcontext.cpp
  rendcontext.h
  render.cpp
  renderglsl.cpp
  renderglsl.h
  render.h
  renderinfo.h
  rotationmanager.cpp
  rotationmanager.h
  selection.cpp
  selection.h
  shadermanager.cpp
  shadermanager.h
  simulation.cpp
  simulation.h
  skygrid.cpp
  skygrid.h
  solarsys.cpp
  solarsys.h
  spheremesh.cpp
  spheremesh.h
  starbrowser.cpp
  starbrowser.h
  starcolors.cpp
  starcolors.h
  star.cpp
  star.h
  stardb.cpp
  stardb.h
  starname.cpp
  starname.h
  staroctree.cpp
  staroctree.h
  stellarclass.cpp
  stellarclass.h
  surface.h
  texmanager.cpp
  texmanager.h
  texture.cpp
  texture.h
  timeline.cpp
  timeline.h
  timelinephase.cpp
  timelinephase.h
  tokenizer.cpp
  tokenizer.h
  trajmanager.cpp
  trajmanager.h
  univcoord.cpp
  univcoord.h
  universe.cpp
  universe.h
  vecgl.h
  virtualtex.cpp
  virtualtex.h
  visibleregion.cpp
  visibleregion.h
)

if(APPLE)
  list(APPEND CELENGINE_SOURCES CGBuffer.h)
endif()

add_library(celengine STATIC ${CELENGINE_SOURCES})
cotire(celengine)
#[[
add_library(celengine SHARED ${CELENGINE_SOURCES})
set_target_properties(celengine PROPERTIES
  VERSION ${VERSION}
  SOVERSION ${VERSION}
)
]]#
add_dependencies(celengine cel3ds celmath celmodel)
target_link_libraries(celengine cel3ds celmath celmodel)
#install(TARGETS celengine LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR})
install(TARGETS celengine ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR})