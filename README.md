# ConsoleGPT

Requires OPENAI_API_KEY environment variable to have been set.

A console helper. Run cgpt.sh, tell the prompt what you want to do, and it will present commands to run. It will first gather various system information (OS, distro, basic configuration stuff) and includes it in the context to get responses relevant to the user's system.

    % cgpt
    Prompt: Print the largest files on my system and how big they are.
    0. Exit
    1. sudo du -ah /. | sort -rh | head -n 20
    2. None of these work. I need to provide more context.
    Choice: 

When you chose a command, it will execute it for you.

Command generation works well enough most of the time. But try as I might, davinci is having difficulty following orders to only produce the commands themselves and sometimes will include descriptions or enumerate resonses in a way to disrupts being able to run them. Right now generation involves a convoluted prompt preparation, and futher efforts should be focused more on a fine-tuned model to generate more predictable output.

Future work should try to fine-tune a model that can be run locally. GPT-J, Llama, OPT, or other. Whichever is more suitable.
