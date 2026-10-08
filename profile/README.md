# KerneLab.ai

**Agentic kernel discovery for AI workloads.**

KerneLab.ai uses state-of-the-art agentic networks to automatically discover optimal kernel strategies for AI workloads. Instead of running your model on a stack of general-purpose kernels, we converge on an application-specific **megakernel**: a single, fused compute kernel shaped around exactly what your workload does.

## Why megakernels

Today's AI workloads are assembled from libraries of hand-tuned, general-purpose kernels. Each one is fast in isolation, but the boundaries between them are expensive:

- **Launch and scheduling overhead** at every kernel boundary
- **Redundant memory traffic** as intermediates are written out and read back in
- **Missed optimizations** that only become visible when operations are considered together
- **Generic code paths** that pay for flexibility your application never uses

A megakernel removes those boundaries. The whole workload is fused, scheduled and laid out in memory as one unit, specialized to your model, your data shapes and your hardware.

## How it works

The space of possible kernel strategies (fusion decisions, scheduling, memory layout, tiling, precision, hardware-specific code generation) is far too large to search by hand, and too irregular for fixed compiler heuristics to cover well. We treat it as a discovery problem.

1. **Profile**: the workload is analyzed to find where time and memory actually go.
2. **Propose**: a network of specialized agents generates candidate kernel strategies.
3. **Verify**: every candidate is compiled, checked for correctness against the reference and benchmarked on the target hardware.
4. **Converge**: measured results feed back into the network, which refines its strategies until it settles on a megakernel for the application.

The output is a megakernel that is specific to one application and validated against it, rather than a general-purpose library.

## Status

KerneLab.ai is a new effort and we are just getting started. New repositories will appear here as we open up our work.

## Get in touch

Follow this organization for updates, or open an issue on one of our repositories once they are public.
