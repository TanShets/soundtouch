cmake_minimum_required(VERSION 3.22.1)

project(SoundTouch)

add_library(SoundTouch STATIC
    source/SoundTouch/AAFilter.cpp
    source/SoundTouch/BPMDetect.cpp
    source/SoundTouch/FIFOSampleBuffer.cpp
    source/SoundTouch/FIRFilter.cpp
    source/SoundTouch/InterpolateCubic.cpp
    source/SoundTouch/InterpolateLinear.cpp
    source/SoundTouch/InterpolateShannon.cpp
    source/SoundTouch/PeakFinder.cpp
    source/SoundTouch/RateTransposer.cpp
    source/SoundTouch/SoundTouch.cpp
    source/SoundTouch/TDStretch.cpp
    source/SoundTouch/cpu_detect_x86.cpp
    source/SoundTouch/mmx_optimized.cpp
    source/SoundTouch/sse_optimized.cpp
)

target_include_directories(SoundTouch PUBLIC
    include
    source/SoundTouch
)

# Enable float samples for better quality
target_compile_definitions(SoundTouch PUBLIC SOUNDTOUCH_FLOAT_SAMPLES=1)
