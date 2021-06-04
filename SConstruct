﻿import os
import platform
import scripts.app_helper as app

helper = app.Helper(ARGUMENTS)
CPPPATH=[
  os.path.join(helper.APP_ROOT, "src/rlottie_impl/inc"),
  os.path.join(helper.APP_ROOT, "src/rlottie_impl/src"),
  os.path.join(helper.APP_ROOT, "src/rlottie_impl/src/lottie"),
  os.path.join(helper.APP_ROOT, "src/rlottie_impl/src/lottie/rapidjson"),
  os.path.join(helper.APP_ROOT, "src/rlottie_impl/src/vector"),
  os.path.join(helper.APP_ROOT, "src/rlottie_impl/src/vector/freetype"),
]

APP_CXXFLAGS = '-DAWTK=1 '

if platform.system() == 'Windows':
  APP_CXXFLAGS += ' /std:c++17 '
else:
  APP_CXXFLAGS += ' -std=c++17 '

helper.add_cpppath(CPPPATH).add_cxxflags(APP_CXXFLAGS)
helper.set_dll_def('src/rlottie.def').set_libs(['rlottie']).call(DefaultEnvironment)

SConscriptFiles = ['src/SConscript', 'demos/SConscript', 'tests/SConscript']
SConscript(SConscriptFiles)
