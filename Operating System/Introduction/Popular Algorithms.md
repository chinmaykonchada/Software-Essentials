# Readers Writers Problem in Operating System (OS)
This is a synchronisation problem which is used to test newly proposed synchronisation scheme. 
- If writer W1 has begun writing process then
    - No additional writer can perform write function
    - No reader is allowed to read
- If 1 or more readers are reading then
    - Other readers may read as well
    - No writer may perform write function until all readers have finished reading
