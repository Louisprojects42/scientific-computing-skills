# Geometry acceptance cases

| Case | Expected handling |
| --- | --- |
| Count line followed by separate surface blocks | Parse as the declared block format; never treat counts as a huge point |
| Reversed ordered contour | Normalize direction with traceable transformation |
| Translated/scaled equivalent | Same normalized shape within declared numerical tolerance |
| Finite trailing-edge gap | Preserve or handle under an explicit blunt-edge convention |
| Scrambled points | Reject as unordered or invoke an explicitly requested reconstruction method |
| Bow-tie crossing | Reject with segment evidence |

Preserve the original file hash and source revision. Report tolerance units and values chosen for the actual downstream task. If a descriptor rejects a candidate pair, establish the relevant conservative bound before claiming no false negatives. An empirical check on a handful of shapes is not such a proof.
