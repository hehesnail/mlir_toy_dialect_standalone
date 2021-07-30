add_mlir_dialect_library(MLIRToy
    Dialect.cpp
    MLIRGen.cpp

    DEPENDS
    MLIRToyOpsIncGen
    MLIRShapeInferenceInterfaceIncGen
    ToyCombineIncGen

    LINK_LIBS PUBLIC
    MLIRIR
    MLIRTransforms
)

add_subdirectory(Passes)