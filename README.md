<!DOCTYPE html>
<html lang="en">
<body>

<h1 align="center">📚 get_next_line – 42 / 1337 Project</h1>
<p align="center">Read a file line by line, like a real programmer.</p>

<!-- Badges -->
<p align="center">
    <img src="https://img.shields.io/badge/Project-get__next__line-blue?style=flat-square">
    <img src="https://img.shields.io/badge/School-1337-black?style=flat-square">
    <img src="https://img.shields.io/badge/Language-C-green?style=flat-square">
</p>

<h2 align="center">🚀 About the Project</h2>
<p>
    <strong>get_next_line</strong> is a project from the <strong>42/1337 curriculum</strong> that teaches students
    how to read text from a file descriptor <strong>line by line</strong>.
    It focuses on mastering static variables, buffer management, memory allocation,
    and safe string manipulation in C.
</p>

<ul>
    <li>Return one line at a time from a file descriptor</li>
    <li>Handle any buffer size</li>
    <li>Manage memory efficiently</li>
    <li>Bonus: Support multiple file descriptors at once</li>
</ul>

<h2 align="center">📁 Project Structure</h2>
<pre>
get_next_line/
│── get_next_line.c
│── get_next_line.h
│── get_next_line_utils.c
│── get_next_line_bonus.c        (bonus)
│── get_next_line_utils_bonus.c  (bonus)
└── README.md
</pre>

<h2 align="center">🧠 What I Learned</h2>
<ul>
    <li>How file descriptors work in low-level C</li>
    <li>Efficient buffer management</li>
    <li>Memory allocation and leak prevention</li>
    <li>Static variables and state persistence</li>
    <li>Handling multiline text streams</li>
    <li>Working with multiple file descriptors</li>
</ul>

<h2 align="center">🔧 Function Prototype</h2>
<pre>
char *get_next_line(int fd);
</pre>

<p>The function returns:</p>
<ul>
    <li>The next line (including <code>\n</code> if present)</li>
    <li><code>NULL</code> if there is nothing left to read or an error occurs</li>
</ul>

<h2 align="center">📦 Mandatory Files</h2>
<ul>
    <li>get_next_line.c</li>
    <li>get_next_line_utils.c</li>
    <li>get_next_line.h</li>
</ul>

<h2 align="center">🧩 Bonus Files</h2>
<ul>
    <li>get_next_line_bonus.c</li>
    <li>get_next_line_utils_bonus.c</li>
</ul>

<h2 align="center">🛠️ Compilation</h2>

<h3>Mandatory version:</h3>
<pre>
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 \
get_next_line.c get_next_line_utils.c main.c
</pre>

<h3>Bonus version:</h3>
<pre>
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 \
get_next_line_bonus.c get_next_line_utils_bonus.c main.c
</pre>

<h2 align="center">📌 Example Usage</h2>
<pre>
#include "get_next_line.h"
#include &lt;fcntl.h&gt;
#include &lt;stdio.h&gt;

int main(void)
{
    int fd = open("test.txt", O_RDONLY);
    char *line;
    while ((line = get_next_line(fd)) != NULL)
    {
        printf("%s", line);
        free(line);
    }
    close(fd);
    return 0;
}
</pre>

<h2 align="center">📜 Makefile Rules</h2>
<ul>
    <li><strong>make</strong> – Compile mandatory part</li>
    <li><strong>make bonus</strong> – Compile bonus version</li>
    <li><strong>make clean</strong> – Remove object files</li>
    <li><strong>make fclean</strong> – Remove object files + binary</li>
    <li><strong>make re</strong> – Rebuild everything</li>
</ul>

<h2 align="center">⚙️ BUFFER_SIZE</h2>
<p>You can compile with any buffer size:</p>
<pre>
cc -D BUFFER_SIZE=1 ...
cc -D BUFFER_SIZE=42 ...
cc -D BUFFER_SIZE=10000 ...
</pre>

<h2 align="center">✔️ Allowed Functions</h2>
<ul>
    <li>read</li>
    <li>malloc</li>
    <li>free</li>
</ul>

<h2 align="center">❌ Forbidden</h2>
<ul>
    <li>lseek</li>
    <li>Global variables</li>
    <li>Using Libft directly</li>
</ul>

<h2 align="center">⭐ Support</h2>
<p align="center">If you like this project, consider starring the repository!</p>

</body>
</html>
