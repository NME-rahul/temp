# Block placement

|Direct Mapping|Set Associative Mapping|Associative Mapping|
|--------------|-----------------------|-------------------|
|Block Number % No. of lines|Block Number % No. of sets|any place|

# Block Identification

1. Direct Mapping
   * |Tag bits|Line No.|Block/Line offset|
     |----|----|----|

   * Find the match using Line No. and Block/Line offset.
   * Compare it with tag associated with the line.
  
3. Set Associative Mapping
   * |Tag bits|Set|Block/Line offset|
     |----|----|----|

   * Find the match using Set No. and Block/Line offset.
   * Compare it with tag associated with the line of only within the set parallel.

4. Associative Mapping
   * |Tag bits|Block/Line offset|
     |----|----|

   * Compare the match with tag associated with every line of cache, simultaneously.
