Cellular basebands play a crucial role in mobile communication. However, it is significantly challenging to assess their security for several reasons. Manual analysis is inevitable because of the obscurity and complexity of baseband firmware; however, such analysis requires repetitive efforts to cover diverse models or versions. Automating the analysis is also non-trivial because the firmware is significantly large and contains numerous functions associated with complex cellular protocols. Therefore, existing approaches on baseband analysis are limited to only a couple of models or versions within a single vendor. In this paper, we propose a novel approach named BaseSpec, which performs a comparative analysis of baseband software and cellular specifications. By leveraging the standardized message structures in the specification, BaseSpec inspects the message structures implemented in the baseband software systematically. It requires a manual yet one-time analysis effort to determine how the message structures are embedded in target firmware. Then, BaseSpec compares the extracted message structures with those in the specification syntactically and semantically, and finally, it reports mismatches. These mismatches indicate the developer mistakes, which break the compliance of the baseband with the specification, or they imply potential vulnerabilities. We evaluated BaseSpec with 18 baseband firmware images of 9 models from one of the top three vendors and found hundreds of mismatches. By analyzing these mismatches, we discovered 9 erroneous cases: 5 functional errors and 4 memory-related vulnerabilities. Notably, two of these are critical remote code execution 0-days. Moreover, we applied BaseSpec to 3 models from another vendor, and BaseSpec found multiple mismatches, two of which led us to discover a buffer overflow bug.