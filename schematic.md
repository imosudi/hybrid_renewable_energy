# Solar Hybrid Inverter System Schematic Layout

## Overview
This schematic layout outlines the interconnection of components for a solar hybrid inverter system designed to power a fish feed pellet production facility. The system supports machinery with a total rated load of approximately 18.2 kW.

## System Components

1. **Solar PV Array (30 kW)**
   - 60 × 500 W Mono/Polycrystalline panels
   - Configured in series-parallel to match inverter input voltage

2. **MPPT Charge Controller (Optional if not integrated)**
   - Rated for total PV output current
   - Manages DC input from panels to batteries

3. **Hybrid Inverter (20 kW)**
   - Pure sine wave output
   - Integrated MPPT, battery, and grid interface
   - AC output for load distribution

4. **Battery Bank (40 kWh)**
   - 8 × 48 V lithium-ion batteries (200Ah each)
   - Connected in parallel/series as needed
   - Fused battery interconnects

5. **AC Load Distribution Box**
   - Circuit breakers for each machine:
     - Extruder (5.5 kW)
     - Grinder (4.0 kW)
     - Mixer (4.0 kW)
     - Dryer (4.7 kW)
   - Surge protection device (SPD)

6. **ATS / Changeover Switch**
   - Select between Solar/Grid/Diesel input
   - Ensures seamless transition during outages

7. **Diesel Generator (Optional Backup)**
   - Minimum 20 kVA
   - Connected via ATS

8. **Grid Connection**
   - Integrated into ATS
   - Used when solar or batteries are low

9. **Monitoring & IoT Dashboard**
   - Smart energy meters (RS485/Modbus to Wi-Fi)
   - Data logger connected to AWS IoT Core
   - Visualisation via Grafana dashboard

## Wiring Flow (Simplified)

```mermaid
graph TD
    A["Solar Panels"] --> B["Combiner Box"]
    B --> C["MPPT Controller"]
    C --> D["Battery Bank"]
    C --> E["Hybrid Inverter"]
    F["Grid / Generator (via ATS)"] --> E
    E --> G["AC Load Distribution"]
    G --> H["Pellet Production Machinery"]
    E --> I["Energy Monitor"]
    I --> J["IoT Gateway"]
    J --> K["AWS IoT"]
    K --> L["Grafana"]
```

## Diagram Sketches

### Basic System Block Diagram (TD Flowchart Style)
```mermaid
graph TD
    A["Solar PV Array"] --> B["Combiner Box"]
    B --> C["MPPT Charge Controller"]
    C --> D["Battery Bank"]
    D --> E["Hybrid Inverter"]
    F["Grid Connection"] --> E
    G["Diesel Generator"] --> E
    E --> H["AC Load Distribution"]
    H --> I["Pellet Machinery"]
    E --> J["Energy Monitor"]
    J --> K["IoT Gateway"]
    K --> L["AWS IoT Core"]
    L --> M["Grafana Dashboard"]
```

### 🔌 Solar-Battery-Inverter Wiring Layout
```mermaid
graph TD
    S1["Solar Panels"] --> S2["Combiner Box"]
    S2 --> S3["MPPT Charge Controller"]
    S3 --> S4["Battery Bank"]
    S3 --> S5["Hybrid Inverter"]
    G1["Grid / Generator (via ATS)"] --> S5
    S5 --> S6["AC Output to Loads"]
```

### ⚙️ Load Distribution Sketch
```mermaid
graph TD
    L1["Hybrid Inverter AC Output"] --> L2["AC Distribution Board"]
    L2 --> L3["Extruder (5.5kW)"]
    L2 --> L4["Grinder (4.0kW)"]
    L2 --> L5["Mixer (4.0kW)"]
    L2 --> L6["Dryer (4.7kW)"]
```

> **Note:** Replace the image URLs with your actual hosted diagram links or relative paths in your project repository.

## Notes
- Ensure all DC wiring is properly fused.
- Use appropriate DC isolators and surge protection.
- Battery management system (BMS) must be integrated for lithium-ion.
- Monitoring gateway must include cellular or Wi-Fi fallback.
- Inverter must be programmed for priority: Solar → Battery → Grid → Generator.

---

Would you like a BOM table added here with model suggestions and prices?
