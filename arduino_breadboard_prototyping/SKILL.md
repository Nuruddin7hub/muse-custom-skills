# Arduino Breadboard Prototyping

## Inventory the actual parts first

- Ask the user to list every part on hand and every power source on hand before you propose wiring.

- Ask for a photo when a part identity is uncertain and read the photo for leg count, markings, and leg lengths.

- Treat a stated constraint as fixed for the whole plan and repeat it back in one short line before you give wiring.

- Do not substitute a part or a power source the user did not list.

## Power the circuit from one source only

- Choose one power source for the test and name the exact entry point it uses.

- Upload code over USB first and then disconnect USB before you connect the test power source.

- Keep a second power source disconnected while the first source powers the circuit.

- Check the supply voltage with a multimeter before you connect a sensitive pin.

- Route any voltage above 5 volts through a divider before it reaches an analog pin and calculate the divider output before you wire it.

- Name the expected reading on the display so a wrong reading points to a wiring error rather than a code error.

## Verify pins before wiring the full circuit

- Identify the longest leg first when a multi leg LED is involved and test each remaining leg through a resistor before you assign it.

- Test one colour at a time and record which pin produces which colour.

- Reverse the common leg test when no colour lights and update the code logic to match the result.

- Wire each leg to its own breadboard row so no two legs share a row.

## Build and test in small stages

- Build power first and confirm the controller and display power up before you add sensors or outputs.

- Add one subsystem at a time and test that subsystem before you add the next one.

- Keep the full code for the current stage in one block and mark any value that changes for a later power source.

- Change only the power entry and the related range when the final supply replaces a test supply.

- Stop at the first failed stage and name the reading or behaviour that failed before you change wiring.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Ask the user to send a photo of the wired breadboard when a description alone leaves a connection unclear.

- Replace a long combined build with a smaller test that proves one behaviour and then expand it.

- Offer a simpler version first when the full version mixes power, sensing, and display in one step.
