# CMakeList.txt : CMake project for GameEngineEditor, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Add source to this project's executable.
add_executable (GameEngineEditor  "GameEngineEditor.cpp")

# @TODO Implement CMakeLists.txt for other platforms than Windows

include_directories(
	"../../Urho3D/build/include"
	"../../Urho3D/build/include/Urho3D/ThirdParty"
	"../../Urho3D/build/include/Urho3D/ThirdParty/Bullet"
)

add_definitions( 
-DWIN32
-D_WINDOWS
-DURHO3D_ANGELSCRIPT
-DURHO3D_FILEWATCHER
-DURHO3D_IK
-DURHO3D_LOGGING
-DURHO3D_MINIDUMPS
-DURHO3D_NAVIGATION
-DURHO3D_NETWORK
-DURHO3D_PHYSICS
-DURHO3D_PHYSICS2D
-DURHO3D_PROFILING
-DURHO3D_THREADING
-DURHO3D_URHO2D
-DURHO3D_WEBP
-DURHO3D_WIN32_CONSOLE
-D_CRT_SECURE_NO_WARNINGS
-D_SCL_SECURE_NO_WARNINGS
-DCMAKE_INTDIR="Debug"
)

target_link_directories(
	GameEngineEditor
	PUBLIC
	"../../Urho3D/build/lib/"
)

target_link_libraries(
	GameEngineEditor
	"Urho3D_d"
	"user32"
	"gdi32"
	"winmm"
	"imm32"
	"ole32"
	"oleaut32"
	"setupapi"
	"version"
	"uuid"
	"ws2_32"
	"iphlpapi"
	"dbghelp"
	"opengl32"
	"kernel32"
	"winspool"
	"shell32"
	"comdlg32"
	"advapi32"
)
set_target_properties(GameEngineEditor PROPERTIES
            CXX_STANDARD 17
            )


# TODO: Add tests and install targets if needed.
