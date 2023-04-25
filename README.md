# Lesson Booking System

A Software Engineering course project: the design and formal modelling of a classroom **lesson-booking system**. Students search rooms and events, make and cancel bookings, join waiting lists, and download receipts, while events are created, validated, and integrated with the university platforms (GOMP and Prodigit).

The repository is split into the analysis/design of the software and an executable formal model that verifies its requirements.

## `design/` — Analysis and design

The full object-oriented design of the system, produced as draw.io diagrams (`design/Grafici/`) and written up in a LaTeX document (`design/Latex/`):

- Use-case diagram and entity class diagram
- Entity–Boundary–Control (EBC) diagram and project class diagram
- Package organization, subsystems and components
- Sequence diagrams (SD) and object life-cycle diagrams for each use case — access/logout, room search, event creation/cancellation, booking and cancellation, waiting lists, event validation/invalidation, and receipt download

## `model/` — Formal model

A Modelica model (`model/Prj/Models/`) that simulates the system and checks it against its requirements. Components include `Aula` (room), `Studenti` (students), `Prenotazioni` (bookings), the `GOMP` and `Prodigit` platform integrations, and two runtime monitors — `Monitor_RF` for functional requirements and `Monitor_RNF` for non-functional requirements — composed together in `System.mo`.

- `run.mos` — OpenModelica script that loads the models and runs the simulation
- `synth.py`, `verify.py` — helper scripts for synthesis and verification, with logs in `log_synth.txt` / `log_verify.txt`
- `Rapporto tecnico.tex` — technical report

## Running the model

With [OpenModelica](https://openmodelica.org/) available:

```bash
cd model/Prj/Models
omc run.mos
```

## Notes

The diagrams, LaTeX documents, and model identifiers are in Italian. The design and the model together form the coursework deliverable.
