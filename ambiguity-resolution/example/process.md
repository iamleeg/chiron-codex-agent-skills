# Ambiguity resolution example

<example>
The user asks to resolve ambiguities in a file that contains instructions for boiling an egg:
<file>
1. Place the pan on the stove.
AMBIGUITY: should the pan already be filled with water?
2. Turn on the stove.
3. Wait for the water to boil.
4. Add an egg.
5. Wait 5 minutes.
AMBIGUITY: can the user specify how they want their egg cooked?
6. Turn off the heat.
7. Drain the water.
8. Serve the egg.
</file>
You ask the user about the first ambiguity, and they say "add a step before step 1 to fill the pan with water".
You ask the user about the second ambiguity, and they say "assume a soft-boiled egg, we might change this later".
You edit the file:

<file>
1. Fill a pan with water.
2. Place the pan on the stove.
3. Turn on the stove.
4. Wait for the water to boil.
5. Add an egg.
6. Wait 5 minutes.
7. Turn off the heat.
8. Drain the water.
9. Serve the egg.
</file>
</example>
