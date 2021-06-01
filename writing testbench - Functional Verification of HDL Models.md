\# The verification challenge is to determine what input patterns (stimulus) to supply to the design and what is the expected output of a properly working desing.

\# apply the stimulus is relatively easy. You are under complete control of its timing and content. It is verifying the response that is difficult.  
\# A designer verifying his own design verifies against his own interpratation, not against the specification.  
\# Verification can only proves the presence of bugs, but not their absence.  
\# Use waveform viewer for debugging not for determinning if a design passes or fails.  
\# Code coverage indicates how thoroughly your entire verification suite exercies the source code. It does not provide an indication in any way about the correctness of the verification suite nor the design.  
\# verifying a specific partition of the design requires a relatively stable interface for the partition.  
# verification plan:  
  - a complete specification document for the design to be verified must exist.  
  - identify which features must be exercied under which conditions and what the
    expected response should be.
  - The feature should be described in terms what needs to be verified, not how
    it is to be implemented.
  - prioritize the features:
    - must-have features: thoroughly verification.
    - should-have features: basic functionality verification.
    - nice-to-have features: time-allowed verification.
  - Component-Level Features:
    - fully contained within the component being verified and do not involve
      system-level interaction with other components.
    - Their correctness can be determined without depending on a subsequent
      verification of the integration of the component into a high-level system.
  - System-Level Features:
    - usually limited to connectivity, flow-control, and inter-operability.
    - question whether it can be verified as a component-level feature instead.
# Unit-level verification:
  - ad-hoc verification process.
  - ensure basic functionality is operational.
  - Partition the design so the features to be verified are completely contained
    within a unit and can be verified on a stand-alone basis.
  - features require interaction with other units, have to be re-verified at a
    higher-level where the features are fully contained, to ensure that the 
    integration correctly implements them.
  - functionality must be verified from the RTL code, before synthesis and implementation.
  - reusable verification component must be verified independent of any one usage.
  - implementing a regression test suite that verifies the compliance of the
    reusable verification component after any modification.
# system-level verification:
  - focuses on the interactions between the individual components instead of the
    functionality implemented in each one.
  -  assume individual components being functionally correct.
# board-level verification:
  - confirm that the connectivity captured by the board design tool is correct.
# verification strategies:
  - decide on the level of granularity.
  - decide on the types of testcases, white-box or black-box.
  - decide on the level of abstraction. 
  - decide on how to verify the response.
# random verification:
  - does not mean randomly apply zeroes and ones to every input signals in the
    design. It is the sequence of these operations and the content of the data
    transferred that is random. 
  - It creates unexpected conditions, hits corner cases, and reduce the bias
    introduced by the verification engineer.
  - The specification (constraits) for a random simulation must include distributions
    and ranges of data and operations.
  - prediction of the expected output is complex.
# testcases:
  - contain a list of the features verified in the testcase.
  - contain a list of the features dependencies assumed to be operational and 
    functionally correct.
  - specify sequence and characteristics of the stimulus and range and distribution
    of random stimulus.
  - expected response and how the response will be determined as valid.
  - Specify what should not happen (errors) and error injection.
# design for verification:
 - planning the verification up front can influence the implementation of the
   design include additional features to aid in verification.
 - provide features for extra controllability (pre-load, by-pass).
 - provide features for extra observability (sample-point).
 

