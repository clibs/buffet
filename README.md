buffet
======

> A clib pointer to https://github.com/alcover/buffet

## Installation

```sh
clib install buffet
```

## Usage

```c
#include <stdio.h>
#include "buffet.h"

int main() {
	char text[] = "The train goes.";

	Buffet own;
	buffet_strcopy (&own, text, sizeof(text));

	Buffet ref = buffet_view (&own, 4, 5);
	buffet_print(&ref); // "train"

	buffet_append (&ref, "ing", 3);
	buffet_print(&ref); // "training"

  Buffet vue;
  buffet_strview (&vue, text+4, 5);
  buffet_print(&vue); // "train"

  text[4] = 'b';
  buffet_print(&vue); // "brain"

  return 0;
}
```

See https://github.com/alcover/buffet for more information.

## License

[GPL](https://github.com/alcover/buffet/blob/main/LICENSE)
