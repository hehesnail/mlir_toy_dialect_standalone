get_property(dialect_libs GLOBAL PROPERTY MLIR_DIALECT_LIBS)
get_property(conversion_libs GLOBAL PROPERTY MLIR_CONVERSION_LIBS)

add_mlir_dialect_library(MLIRToyTransforms
    LowerToAffineLoops.cpp
    LowerToLLVM.cpp
    ShapeInferencePass.cpp
    ToyCombine.cpp

    DEPENDS
    MLIRToyOpsIncGen
    MLIRShapeInferenceInterfaceIncGen
    ToyCombineIncGen

    LINK_LIBS PUBLIC
    ${dialect_libs}
    ${conversion_libs}
    MLIRAnalysis
    MLIRIR
    MLIRPass
    MLIRSideEffectInterfaces
    MLIRTransforms
    MLIRCallInterfaces
    MLIRCastInterfaces
)