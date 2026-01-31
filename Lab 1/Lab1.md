<!-- Lab 1: Connection of Network Devices Using Ethernet -->

# Lab 1: Connection of Network Devices Using Ethernet

## Step 1: Preparation of Ethernet Cable with RJ45 Connectors

### Materials Required:
- Ethernet cable (Cat5e or Cat6)
- RJ45 connectors
- Crimping tool
- Wire stripper
- Cable tester

### Procedure:

#### Type 1: Straight-through Cable
1. Cut the Ethernet cable to the desired length.
2. Strip about 1 inch of the outer jacket from both ends of the cable using the wire stripper.
3. Untwist the pairs of wires and arrange them according to the T568B wiring standard:
   - Pin 1: White/Orange
   - Pin 2: Orange
   - Pin 3: White/Green
   - Pin 4: Blue
   - Pin 5: White/Blue
   - Pin 6: Green
   - Pin 7: White/Brown
   - Pin 8: Brown
4. Trim the wires to ensure they are all the same length.
5. Insert the wires into the RJ45 connector, ensuring each wire goes into its respective slot.
6. Use the crimping tool to secure the RJ45 connector onto the cable.
7. Repeat steps 2-6 for the other end of the cable.
8. Test the cable using a cable tester to ensure proper connectivity.

#### Type 2: Crossover Cable
1. Follow steps 1-4 from the straight-through cable procedure.
2. For one end of the cable, arrange the wires according to the T568A wiring standard:
   - Pin 1: White/Green
   - Pin 2: Green
   - Pin 3: White/Orange
   - Pin 4: Blue
   - Pin 5: White/Blue
   - Pin 6: Orange
   - Pin 7: White/Brown
   - Pin 8: Brown
3. For the other end of the cable, arrange the wires according to the T568B wiring standard:
   - Pin 1: White/Orange
   - Pin 2: Orange
   - Pin 3: White/Green
   - Pin 4: Blue
   - Pin 5: White/Blue
   - Pin 6: Green
   - Pin 7: White/Brown
   - Pin 8: Brown
4. Trim the wires to ensure they are all the same length.
5. Insert the wires into the RJ45 connectors, ensuring each wire goes into its respective slot.
6. Use the crimping tool to secure the RJ45 connectors onto the cable.
7. Test the cable using a cable tester to ensure proper connectivity.

## Connection Testing Using Cable Tester
1. Connect one end of the cable to the transmitter unit of the cable tester.
2. Connect the other end of the cable to the receiver unit of the cable tester.
3. Turn on the cable tester and observe the results.

- For a straight-through cable, all pairs should show continuity in the same order. For a crossover cable, the transmit and receive pairs should be crossed.
- Orders : 1-8 for straight-through and 1-3, 2-6, 3-1, 6-2 for crossover.

## Output
   ### Straight-through Cable Test Results:
- ![Network Cable Tester : 1-1 (Straight Through)](straight/st_1.jpg "Network Cable Tester : 1-1 (Straight Through)")
*Fig : Network Cable Tester : 1-1 (Straight Through)*

- ![Network Cable Tester : 2-2 (Straight Through)](straight/st_2.jpg "Network Cable Tester : 2-2 (Straight Through)")
*Fig : Network Cable Tester : 2-2 (Straight Through)*

- ![Network Cable Tester : 3-3 (Straight Through)](straight/st_3.jpg "Network Cable Tester : 3-3 (Straight Through)")
*Fig : Network Cable Tester : 3-3 (Straight Through)*

- ![Network Cable Tester : 4-4 (Straight Through)](straight/st_4.jpg "Network Cable Tester : 4-4 (Straight Through)")
*Fig : Network Cable Tester : 4-4 (Straight Through)*

- ![Network Cable Tester : 5-5 (Straight Through)](straight/st_5.jpg "Network Cable Tester : 5-5 (Straight Through)")
*Fig : Network Cable Tester : 5-5 (Straight Through)*

- ![Network Cable Tester : 6-6 (Straight Through)](straight/st_6.jpg "Network Cable Tester : 6-6 (Straight Through)")
*Fig : Network Cable Tester : 6-6 (Straight Through)*

- ![Network Cable Tester : 7-7 (Straight Through)](straight/st_7.jpg "Network Cable Tester : 7-7 (Straight Through)")
*Fig : Network Cable Tester : 7-7 (Straight Through)*

- ![Network Cable Tester : 8-8 (Straight Through)](straight/st_8.jpg "Network Cable Tester : 8-8 (Straight Through)")
*Fig : Network Cable Tester : 8-8 (Straight Through)*

- ![RJ45 Connectors on Straight-through Cable](straight/1.jpg "RJ45 Connectors on Straight-through Cable")
*Fig : RJ45 Connectors on Straight-through Cable*


   ### Crossover Cable Test Results:
- ![Network Cable Tester : 1-3 (Crossover)](crossover/co_1.jpg "Network Cable Tester : 1-3 (Crossover)")
*Fig : Network Cable Tester : 1-3 (Crossover)*

- ![Network Cable Tester : 2-6 (Crossover)](crossover/co_2.jpg "Network Cable Tester : 2-6 (Crossover)")
*Fig : Network Cable Tester : 2-6 (Crossover)*

- ![Network Cable Tester : 3-1 (Crossover)](crossover/co_3.jpg "Network Cable Tester : 3-1 (Crossover)")
*Fig : Network Cable Tester : 3-1 (Crossover)*

- ![Network Cable Tester : 4-4 (Crossover)](crossover/co_4.jpg "Network Cable Tester : 4-4 (Crossover)")
*Fig : Network Cable Tester : 4-4 (Crossover)*

- ![Network Cable Tester : 5-5 (Crossover)](crossover/co_5.jpg "Network Cable Tester : 5-5 (Crossover)")
*Fig : Network Cable Tester : 5-5 (Crossover)*

- ![Network Cable Tester : 6-2 (Crossover)](crossover/co_6.jpg "Network Cable Tester : 6-2 (Crossover)")
*Fig : Network Cable Tester : 6-2 (Crossover)*

- ![Network Cable Tester : 7-7 (Crossover)](crossover/co_7.jpg "Network Cable Tester : 7-7 (Crossover)")
*Fig : Network Cable Tester : 7-7 (Crossover)*

- ![Network Cable Tester : 8-8 (Crossover)](crossover/co_8.jpg "Network Cable Tester : 8-8 (Crossover)")
*Fig : Network Cable Tester : 8-8 (Crossover)*

- ![RJ45 Connectors on Crossover Cable](crossover/rj45_co.jpg "RJ45 Connectors on Crossover Cable")
*Fig : RJ45 Connectors on Crossover Cable*



## Results:
- The cable tester should indicate that all wires are properly connected and there are no faults.
- Visible Outputs are shown in images in the sub-folders straight and crossover.