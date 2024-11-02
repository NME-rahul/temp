# SLR(1)

## Limitations of SLR(1) parsers

### Shift-Reduce and Reduce-Reduce
### Conflict Due to limited grammar coverage
SLR(1) parser uses only _follow()_ set to decide reduce move which limits its view to cover entire grammar
