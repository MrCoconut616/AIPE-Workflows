# Clean-checkout acceptance run, 2026-10-22 (after the tool consolidation)

Same harness and sources as `acceptance-2026-10-21`, executed 22:55–22:59 local (14:55–14:59 UTC) in the relocated workspace
`D:\Cursor Workspace\AIPE-Full-Ecosystem-Integration\acc` (56-character prefix, longest resulting path 247 characters)
with every engineering tool under `D:\EngineeringTools`: KiCad 10.0.7 (`AIPE_KICAD_CLI`), FreeCAD 1.1.4 (`AIPE_FREECADCMD`),
ngspice 47 and Elmer 9.0 (`AIPE_TOOLS_DIR`, doctor source `tools-dir`), Gmsh 4.15.2 (pip). Repositories at the same PR heads as
on 2026-10-21 except AIPE-PCB-Agent (33cd48d, CI fixes) and AIPE-Workflows (610a415, doctor/FEM-adapter fixes).

Result: every step exit 0 except the workflow run (exit 2, `completed_with_failed_optional`: `pcb-erc-drc` fails by design
with 0 DRC errors and 26/23/24 open connections); gates analytical/software/circuit_simulation/field_simulation pass,
cad_pcb fail; `verify` reports no artifact problems and no Engineering-State errors. The leaf-by-leaf comparison with the
2026-10-21 run (`comparison-with-acceptance-2026-10-21.txt`) shows identical engineering values; only run-specific evidence
ids differ, plus the KiCad version recorded in the PCB reports (10.0.7 instead of 10.0.6).

| File | Content |
| --- | --- |
| `acceptance.log` | commands, exit codes, clone commits, pip list, doctor output, contract tests, workflow output |
| `doctor.json` | tool qualification with the `D:\EngineeringTools` paths and sources |
| `plan.json`, `run.json`, `verification.json` | planned tasks, run state, gates |
| `sources-used.json` | the sources file (workspace, tools_dir, environment, repositories and refs) |
