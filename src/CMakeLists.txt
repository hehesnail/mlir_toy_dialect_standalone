add_llvm_executable(toy_main
    toyc.cpp
    AST.cpp
)

target_link_libraries(toy_main PRIVATE
    # LLVMCore
    # LLVMSupport
    # LLVMnativecodegen
    # LLVMOrcJIT

    MLIRToy
    MLIRToyTransforms

    MLIRAnalysis
    MLIRCallInterfaces
    MLIRCastInterfaces
    MLIRExecutionEngine
    MLIRIR
    MLIRLLVMToLLVMIRTranslation
    MLIRParser
    MLIRPass
    MLIRSideEffectInterfaces
    MLIRTargetLLVMIRExport
    MLIRTransforms
)
