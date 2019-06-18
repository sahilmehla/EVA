| TYPE              | Kernel  | Stride |  Receptive Field | Jump In     |
| :------------------- | --------------- | -------   | --------- | -------------------- | 
| input - 224x224 |             |           |  1  |  1  |
| convolution  |   7x7          |    2     |       7          |   1      |
| max pool      |   3x3          |    2     |       11          |    2     |
| convolution  |   3x3          |    1    |        19         |   4      |
| max pool      |   3x3          |    2     |       27          |    4     |
| inception      |   5x5          |    1     |       59          |    8     |
| inception      |   5x5          |    1    |        91        |     8    |
| max pool      |   3x3          |    2    |      107           |    8     |
| inception      |   5x5          |   1     |      171           |   16      |
| inception      |   5x5          |   1    |        235         |     16    |
| inception      |   5x5          |   1    |      299           |     16    |
| inception      |   5x5          |   1    |     363            |     16    |
| inception      |   5x5          |   1    |      427           |     16    |
| max pool      |   3x3          |   2    |      459           |     16    |
| inception      |   5x5          |   1    |            587     |     32    |
| inception      |   5x5          |    1   |         715        |      32   |
| avg pool       |    7x7         |    1   |         907        |     32    |
