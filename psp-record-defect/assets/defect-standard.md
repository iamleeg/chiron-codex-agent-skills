# PSP Defect Type Standard

| Type Number | Type Name | Description |
|-------------|-----------|-------------|
|10|Documentation|Including user instructions, documentation comments, general problems with comments|
|20|Syntax|Typos, missing punctuation, incorrect keywords|
|30|Build or Package|Version control, change management, or dependency problems|
|40|Assignment|Missing declarations, duplicate names, incorrect scope or visibility|
|50|Interface|Hallucinated APIs, APIs that aren't available on the platform, or trying to use protected interfaces|
|60|Checking|Lack of error/failure checking, assertion not satisfied, or missing error messages|
|70|Data|Incorrect data structures or content|
|80|Logic|Incorrect loops, recursion, computation, tests, or other failure of a function to satisfy its contract|
|90|Memory|Incorrect pointer use, use-after-free, stack overwriting, ASan issue, zombie pointer, memory leak|
|100|Threading|Running code on the wrong thread, timing issues, deadlocks/livelocks, multiple unsynchronized writers, TSan issue|
|110|System|Configuration issues, missing files, unset environment variables|
|120|Support|Problems with design artifacts, project plans, requirements, or tools|
