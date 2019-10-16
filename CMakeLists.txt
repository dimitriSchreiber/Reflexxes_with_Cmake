# cmake_minimum_required(VERSION <specify CMake version here>)

cmake_minimum_required(VERSION 3.10)
project(ReflexxesTypeII)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -pthread")

include_directories(include)

#not needed if this becomes a catkin project --> static
add_library(${PROJECT_NAME} STATIC
		include/ReflexxesAPI.h
        include/RMLFlags.h
        include/RMLInputParameters.h
        include/RMLOutputParameters.h
        include/RMLPositionFlags.h
        include/RMLPositionInputParameters.h
        include/RMLPositionOutputParameters.h
        include/RMLVector.h
        include/RMLVelocityFlags.h
        include/RMLVelocityInputParameters.h
        include/RMLVelocityOutputParameters.h
        include/TypeIIRMLDecisions.h
        include/TypeIIRMLDecisionTree1A.h
        include/TypeIIRMLDecisionTree1B.h
        include/TypeIIRMLDecisionTree1C.h
        include/TypeIIRMLDecisionTree2.h
        include/TypeIIRMLMath.h
        include/TypeIIRMLPolynomial.h
        include/TypeIIRMLPosition.h
        include/TypeIIRMLQuicksort.h
        include/TypeIIRMLStep1IntermediateProfiles.h
        include/TypeIIRMLStep1Profiles.h
        include/TypeIIRMLStep2IntermediateProfiles.h
        include/TypeIIRMLStep2Profiles.h
        include/TypeIIRMLStep2WithoutSynchronization.h
        include/TypeIIRMLVelocity.h
        src/TypeIIRML/ReflexxesAPI.cpp
        src/TypeIIRML/TypeIIRMLCalculatePositionalExtrems.cpp
        src/TypeIIRML/TypeIIRMLDecisions.cpp
        src/TypeIIRML/TypeIIRMLDecisionTree1A.cpp
        src/TypeIIRML/TypeIIRMLDecisionTree1B.cpp
        src/TypeIIRML/TypeIIRMLDecisionTree1C.cpp
        src/TypeIIRML/TypeIIRMLDecisionTree2.cpp
        src/TypeIIRML/TypeIIRMLFallBackStrategy.cpp
        src/TypeIIRML/TypeIIRMLIsPhaseSynchronizationPossible.cpp
        src/TypeIIRML/TypeIIRMLPolynomial.cpp
        src/TypeIIRML/TypeIIRMLPosition.cpp
        src/TypeIIRML/TypeIIRMLQuicksort.cpp
        src/TypeIIRML/TypeIIRMLSetupModifiedSelectionVector.cpp
        src/TypeIIRML/TypeIIRMLStep1.cpp
        src/TypeIIRML/TypeIIRMLStep1IntermediateProfiles.cpp
        src/TypeIIRML/TypeIIRMLStep1Profiles.cpp
        src/TypeIIRML/TypeIIRMLStep2.cpp
        src/TypeIIRML/TypeIIRMLStep2IntermediateProfiles.cpp
        src/TypeIIRML/TypeIIRMLStep2PhaseSynchronization.cpp
        src/TypeIIRML/TypeIIRMLStep2Profiles.cpp
        src/TypeIIRML/TypeIIRMLStep2WithoutSynchronization.cpp
        src/TypeIIRML/TypeIIRMLStep3.cpp
        src/TypeIIRML/TypeIIRMLVelocity.cpp
        src/TypeIIRML/TypeIIRMLVelocityCalculatePositionalExtrems.cpp
        src/TypeIIRML/TypeIIRMLVelocityFallBackStrategy.cpp
        src/TypeIIRML/TypeIIRMLVelocityIsPhaseSynchronizationPossible.cpp
        src/TypeIIRML/TypeIIRMLVelocityMethods.cpp
        src/TypeIIRML/TypeIIRMLVelocitySetupPhaseSyncSelectionVector.cpp
)

#not needed if this becomes a catkin project
set(ReflexxesTypeII_INCLUDE_DIRS
 ${PROJECT_SOURCE_DIR}/include
 CACHE INTERNAL "${PROJECT_NAME}: Include Directories" FORCE)

#not needed if this becomes a catkin project
set_target_properties(${PROJECT_NAME}
        PROPERTIES POSITION_INDEPENDENT_CODE ON)

add_executable(ReflexxesTypeII_demo
        src/RMLPositionSampleApplications/03_RMLPositionSampleApplication.cpp)

target_link_libraries(ReflexxesTypeII_demo ${PROJECT_NAME})
