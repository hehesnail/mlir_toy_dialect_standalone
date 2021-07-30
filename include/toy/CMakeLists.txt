# Most dialects should use add_mlir_dialect().  See examples/standalone.
set(LLVM_TARGET_DEFINITIONS Ops.td)
mlir_tablegen(Ops.h.inc -gen-op-decls)
mlir_tablegen(Ops.cpp.inc -gen-op-defs)
mlir_tablegen(Dialect.h.inc -gen-dialect-decls)
add_public_tablegen_target(MLIRToyOpsIncGen)

# add_mlir_dialect(ToyOps toy)
# add_mlir_doc(ToyDialect -gen-dialect-doc ToyDialect toy/)
# add_mlir_doc(ToyOps -gen-op-doc ToyOps toy/ )

add_subdirectory(Passes)
