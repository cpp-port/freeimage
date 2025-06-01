cmake_minimum_required(VERSION 3.16)
project(freeimage CXX)

#set(VERSION "1.2.11")

#option(ASM686 "Enable building i686 assembly implementation")
#option(AMD64 "Enable building amd64 assembly implementation")

#set(INSTALL_BIN_DIR "${CMAKE_INSTALL_PREFIX}/bin" CACHE PATH "Installation directory for executables")
#set(INSTALL_LIB_DIR "${CMAKE_INSTALL_PREFIX}/lib" CACHE PATH "Installation directory for libraries")
#set(INSTALL_INC_DIR "${CMAKE_INSTALL_PREFIX}/include" CACHE PATH "Installation directory for headers")
#set(INSTALL_MAN_DIR "${CMAKE_INSTALL_PREFIX}/share/man" CACHE PATH "Installation directory for manual pages")
#set(INSTALL_PKGCONFIG_DIR "${CMAKE_INSTALL_PREFIX}/share/pkgconfig" CACHE PATH "Installation directory for pkgconfig (.pc) files")

#include(CheckTypeSize)
#include(CheckFunctionExists)
#include(CheckIncludeFile)
#include(CheckCSourceCompiles)
#enable_testing()

if (MSVC)
    set(CMAKE_DEBUG_POSTFIX "d")
    add_definitions(-D_CRT_SECURE_NO_DEPRECATE)
    add_definitions(-D_CRT_NONSTDC_NO_DEPRECATE)
    include_directories(${CMAKE_CURRENT_SOURCE_DIR})
endif ()


#set(ZLIB_PC ${CMAKE_CURRENT_BINARY_DIR}/zlib.pc)
#configure_file( ${CMAKE_CURRENT_SOURCE_DIR}/zlib.pc.cmakein
#		${ZLIB_PC} @ONLY)
#configure_file(	${CMAKE_CURRENT_SOURCE_DIR}/zconf.h.cmakein
#		${CMAKE_CURRENT_BINARY_DIR}/zconf.h @ONLY)
#include_directories(${CMAKE_CURRENT_BINARY_DIR} ${CMAKE_SOURCE_DIR})


#set(IDN_PUBLIC_HDRS
#   idn/idna.h
#)

#target_include_directories(idn PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../..)


list(APPEND library_source
        Source/FreeImage/BitmapAccess.cpp
        Source/FreeImage/ColorLookup.cpp
        Source/FreeImage/ConversionRGBA16.cpp
        Source/FreeImage/ConversionRGBAF.cpp
        Source/FreeImage/FreeImage.cpp
        Source/FreeImage/FreeImageC.c
        Source/FreeImage/FreeImageIO.cpp
        Source/FreeImage/GetType.cpp
        Source/FreeImage/LFPQuantizer.cpp
        Source/FreeImage/MemoryIO.cpp
        Source/FreeImage/PixelAccess.cpp
        Source/FreeImage/J2KHelper.cpp
        Source/FreeImage/MNGHelper.cpp
        Source/FreeImage/Plugin.cpp
        Source/FreeImage/PluginBMP.cpp
        Source/FreeImage/PluginCUT.cpp
        Source/FreeImage/PluginDDS.cpp
        Source/FreeImage/PluginEXR.cpp
        Source/FreeImage/PluginG3.cpp
        Source/FreeImage/PluginGIF.cpp
        Source/FreeImage/PluginHDR.cpp
        Source/FreeImage/PluginICO.cpp
        Source/FreeImage/PluginIFF.cpp
        Source/FreeImage/PluginJ2K.cpp
        Source/FreeImage/PluginJNG.cpp
        Source/FreeImage/PluginJP2.cpp
        Source/FreeImage/PluginJPEG.cpp
        Source/FreeImage/PluginJXR.cpp
        Source/FreeImage/PluginKOALA.cpp
        Source/FreeImage/PluginMNG.cpp
        Source/FreeImage/PluginPCD.cpp
        Source/FreeImage/PluginPCX.cpp
        Source/FreeImage/PluginPFM.cpp
        Source/FreeImage/PluginPICT.cpp
        Source/FreeImage/PluginPNG.cpp
        Source/FreeImage/PluginPNM.cpp
        Source/FreeImage/PluginPSD.cpp
        Source/FreeImage/PluginRAS.cpp
        Source/FreeImage/PluginRAW.cpp
        Source/FreeImage/PluginSGI.cpp
        Source/FreeImage/PluginTARGA.cpp
        Source/FreeImage/PluginTIFF.cpp
        Source/FreeImage/PluginWBMP.cpp
        Source/FreeImage/PluginWebP.cpp
        Source/FreeImage/PluginXBM.cpp
        Source/FreeImage/PluginXPM.cpp
        Source/FreeImage/PSDParser.cpp
        Source/FreeImage/TIFFLogLuv.cpp
        Source/FreeImage/Conversion.cpp
        Source/FreeImage/Conversion16_555.cpp
        Source/FreeImage/Conversion16_565.cpp
        Source/FreeImage/Conversion24.cpp
        Source/FreeImage/Conversion32.cpp
        Source/FreeImage/Conversion4.cpp
        Source/FreeImage/Conversion8.cpp
        Source/FreeImage/ConversionFloat.cpp
        Source/FreeImage/ConversionRGB16.cpp
        Source/FreeImage/ConversionRGBF.cpp
        Source/FreeImage/ConversionType.cpp
        Source/FreeImage/ConversionUINT16.cpp
        Source/FreeImage/Halftoning.cpp
        Source/FreeImage/tmoColorConvert.cpp
        Source/FreeImage/tmoDrago03.cpp
        Source/FreeImage/tmoFattal02.cpp
        Source/FreeImage/tmoReinhard05.cpp
        Source/FreeImage/ToneMapping.cpp
        Source/FreeImage/NNQuantizer.cpp
        Source/FreeImage/WuQuantizer.cpp
        Source/DeprecationManager/Deprecated.cpp
        Source/DeprecationManager/DeprecationMgr.cpp
        Source/FreeImage/CacheFile.cpp
        Source/FreeImage/MultiPage.cpp
        Source/FreeImage/ZLibInterface.cpp
        Source/Metadata/Exif.cpp
        Source/Metadata/FIRational.cpp
        Source/Metadata/FreeImageTag.cpp
        Source/Metadata/IPTC.cpp
        Source/Metadata/TagConversion.cpp
        Source/Metadata/TagLib.cpp
        Source/Metadata/XTIFF.cpp
        Source/FreeImageToolkit/Background.cpp
        Source/FreeImageToolkit/BSplineRotate.cpp
        Source/FreeImageToolkit/Channels.cpp
        Source/FreeImageToolkit/ClassicRotate.cpp
        Source/FreeImageToolkit/Colors.cpp
        Source/FreeImageToolkit/CopyPaste.cpp
        Source/FreeImageToolkit/Display.cpp
        Source/FreeImageToolkit/Flip.cpp
        Source/FreeImageToolkit/JPEGTransform.cpp
        Source/FreeImageToolkit/MultigridPoissonSolver.cpp
        Source/FreeImageToolkit/Rescale.cpp
        Source/FreeImageToolkit/Resize.cpp
        Source/CacheFile.h
        Source/DeprecationManager/DeprecationMgr.h
        Source/MapIntrospector.h
        Source/Metadata/FIRational.h
        Source/FreeImage.h
        Source/FreeImageIO.h
        Source/Metadata/FreeImageTag.h
        Source/FreeImage/J2KHelper.h
        Source/Plugin.h
        Source/FreeImage/PSDParser.h
        Source/Quantizers.h
        Source/ToneMapping.h
        Source/Utilities.h
        Source/FreeImageToolkit/Resize.h
)

list(APPEND library_references
        jpeg
        jxr
        openexr
        openjpeg
        tiff4
)


add_library(${PROJECT_NAME} SHARED ${library_source})

target_link_libraries(${PROJECT_NAME} ${library_references})


target_compile_definitions(${PROJECT_NAME} PRIVATE HAVE_CONFIG_H INITGUID)
if(MSVC)
    target_compile_definitions(${PROJECT_NAME} PRIVATE OPENEXR_DLL)
endif()


target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/..)
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../webp)
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../jxr/common)
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include/FreeImage)
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../../../operating_system/operating_system-${OPERATING_SYSTEM_LOWERED_NAME}/configuration/FreeImage)

#add_library(${PROJECT_NAME}_static STATIC ${ZLIB_SRCS} ${ZLIB_ASMS} ${ZLIB_PUBLIC_HDRS} ${ZLIB_PRIVATE_HDRS})
set_target_properties(${PROJECT_NAME} PROPERTIES DEFINE_SYMBOL FREEIMAGE_DLL)
#set_target_properties(${PROJECT_NAME} PROPERTIES SOVERSION 1)


