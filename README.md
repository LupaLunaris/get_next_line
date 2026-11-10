# get_next_line

A C function that reads one line at a time from a file descriptor. Built for the 42 curriculum.

It keeps any unread bytes between calls, allowing the caller to process a file incrementally rather than loading everything into memory.

## Usage

The public function is declared in `get_next_line.h`:

```c
char *get_next_line(int fd);
```

The caller owns the returned line and must free it. A `NULL` return indicates that no line was returned.

Compile it with a chosen buffer size:

```bash
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 \
  get_next_line.c get_next_line_utils.c your_main.c -o read_lines
```

Bonus sources for working with multiple file descriptors are also included.

## What I learned

This was useful practice with static state, dynamic memory, file descriptors and edge cases around the end of a file.
