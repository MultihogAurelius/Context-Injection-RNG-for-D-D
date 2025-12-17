This is a system that rolls random numbers and invisibly prepends them to the input (the message you send) in the following manner: 

role: 'user',
      content: '[RNG_QUEUE v1]\n' +
        'turn_id=1765963064489\n' +
        'scope=this_response\n' +
        'queue=16,12,13,11,11,6,8,2,15,14,6,16,12,3,4,18,8,11,3,11\n' +
        'rule=ABSOLUTE LAW: use in order. For rolls < d20 (e.g. damage), use value modulo die size (or clamp).\n' +
        '[/RNG_QUEUE]\n' +
        '\n' +
        'test'
This makes it so that the AI has an "RNG bank" always available that it will use for its rolls, ensuring real randomness. This bank refreshes every input/output.

This is an alternative to using function calls. One advantage it has is seamlessness. You don't need to pay for multiple outputs because it all happens within one output.

The system works best in CYOA mode, where the model suggests potential courses of action with the DC (difficulty check) values attached. This way, the AI commits to the DC *before* it gains knowledge of the random number that will be used for that check. If you want to ensure freeform actions are similarly fair, you should supply the DC yourself in your input.

It works well with the system prompt I've attached.

**How to install**: 
1. Unzip the folder into SillyTavern\public\scripts\extensions\third-party\
2. Press F5 if SillyTavern is already running
3. Enable in extensions
