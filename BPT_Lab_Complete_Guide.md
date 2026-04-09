# BPT LAB RECORD -- COMPLETE GUIDE
### Bioprocess Technology Laboratory | All 7 Experiments
### Detailed Explanations in Simple Language + Viva Questions (Basic to Advanced)

---
---

# EXPERIMENT 1: DESIGN AND LAYOUT OF A FERMENTER

## Aim
To study and understand the design, components, and working layout of a standard laboratory fermenter (stirred tank reactor).

---

## Detailed Explanation in Simple Words

A fermenter is just a fancy sealed container used to grow microorganisms -- bacteria, yeast, fungi, or even animal/plant cells. Think of it like a pressure cooker, but instead of cooking food, you are "cooking" tiny living things so they produce something useful -- antibiotics, enzymes, alcohol, organic acids, vaccines, insulin, etc.

The full name is **Stirred Tank Reactor (STR)** or **Bioreactor**. It is a cylindrical tank fitted with a motor-driven stirrer and lots of sensors and pipes.

Why do we even need a fermenter? Because microorganisms are fussy. They need:
- The right temperature (not too hot, not too cold)
- The right pH (not too acidic, not too alkaline)
- Enough oxygen (for aerobic organisms)
- Proper nutrients mixed evenly
- No contamination from unwanted microbes

A fermenter controls all of this automatically.

---

## Components of a Fermenter -- What Each Part Does

### A. Structural Components (The Body)

| Part | What It Does | Why It Matters |
|------|-------------|----------------|
| **Top Plate** | The steel lid that sits on top of the vessel | Provides access ports for probes, additions, and the drive shaft |
| **Clamp** | Holds the top plate tightly onto the vessel | Without it, the lid would blow off under pressure or leak |
| **Seal (Gasket)** | Rubber/silicone ring between the lid and vessel | Prevents air from leaking in or out. Maintains sterility |
| **Vessel** | The main tank body. Can be glass (lab-scale, 1-20L) or stainless steel (industrial, 100L to 100,000L+) | Has ports for inputs, outputs, probes, and sampling |
| **Drive Motor** | Electric motor mounted on top | Rotates the drive shaft at controlled speeds (RPM) |
| **Drive Shaft** | A vertical rod that goes from the motor down into the liquid | Has impellers (blades) attached to it for mixing |
| **Impellers** | Blades attached to the drive shaft | Create flow patterns that mix the medium, distribute nutrients, and break air bubbles into smaller ones for better oxygen transfer |
| **Marine Impeller** | A specific type of impeller with angled blades | Gives gentle axial (top-to-bottom) flow. Used for shear-sensitive cultures like plant tissue and animal cells |
| **Rushton Turbine** | Flat-blade disc impeller (not marine type) | Gives strong radial flow with high shear. Good for bacterial cultures and breaking air bubbles |
| **Baffles** | 4 vertical metal strips welded to the inside wall | Prevent the liquid from just spinning in a circle (vortex). Force proper top-to-bottom mixing |

### B. Input/Output Systems

| Part | What It Does | Why It Matters |
|------|-------------|----------------|
| **Sparger** | A device at the bottom that introduces sterile air as fine bubbles | Provides dissolved oxygen for aerobic organisms. Air passes through a filter first to remove contaminants |
| **Air Filter** | Membrane or depth filter on the air line before the sparger | Removes bacteria and fungi from incoming air so the culture stays sterile |
| **Exit Gas Cooler (Condenser)** | Cools the exhaust gas before it leaves | Recovers moisture that would otherwise be lost. Also prevents contamination from entering through the exhaust |
| **Inoculation Needle/Port** | A sealed port for adding the starter culture (inoculum) | Allows aseptic (sterile) addition of microorganisms |
| **Feed Pumps** | Variable-speed pumps for adding nutrients, medium, acids, bases | Allow controlled feeding -- you can add nutrients slowly (fed-batch) or maintain pH automatically |
| **Peristaltic Pumps** | Fixed-speed pumps that squeeze a tube to move liquid | Used for continuous sampling, adding anti-foam, or continuous culture operations |
| **Syringe Pump** | Pushes liquid from a syringe at a very precise rate | Used mostly in small-scale batch operations where exact volumes matter |
| **Sample Pipe** | A tube through which you can pull out small amounts of the culture | Allows you to check on the culture without opening the fermenter |
| **3-Way Inlet** | A port that splits into three paths | Lets you insert different probes or tubes into the vessel through one opening |
| **Harvest Line** | An outlet at the bottom or side of the vessel | Used to drain the finished product at the end of fermentation |
| **Steam Inlet/Outlet** | Ports for steam sterilization | Before use, the fermenter is sterilized with high-pressure steam (121 deg C, 15 psi, 20 min) |

### C. Monitoring and Control Systems (The Brain)

| Sensor/Device | What It Measures/Does | Details |
|--------------|----------------------|---------|
| **Pt100** | Temperature | Platinum Resistance Thermometer. Its resistance changes with temperature. Very accurate (0.1 deg C precision) |
| **Foam Probe** | Detects foam formation | Placed above the liquid level. When foam rises and touches it, it triggers the anti-foam pump to add defoamer |
| **pH Electrode** | Measures the acidity/alkalinity of the medium | Connected to a controller that automatically adds acid or base to keep pH at the set point |
| **O2 Sensor (DO Probe)** | Measures dissolved oxygen in the liquid | If DO drops below a set level, the controller can increase agitation speed or air flow rate |
| **Heater Pad** | Heats the vessel | Direct contact heater. Used to raise temperature quickly |
| **Cold Finger** | Cools the vessel | A coil through which cold water flows. Used after direct heating or to remove metabolic heat |
| **Cold Water Jacket** | Surrounds the vessel body | Circulates cold water to maintain constant temperature. Microbial metabolism generates heat, so this keeps things cool |
| **Rotameter** | Measures air flow rate | A variable-area flow meter. A float inside a tapered tube rises higher with more air flow. Attached to the sparger line |
| **Pressure Valve** | Controls internal pressure | Safety device. Releases pressure if it builds up too much. Also maintains positive pressure to prevent contamination |
| **Temperature Recorder and Controller** | Records temperature over time and adjusts heating/cooling | Keeps a log of the entire fermentation and makes automatic adjustments |
| **pH Control Device** | Automatically adjusts pH | Reads pH, compares to set point, and pumps acid or base as needed |
| **Anti-Foam Agent Tank** | Stores chemical defoamer (like silicone oil) | When foam probe is triggered, a small amount of anti-foam is pumped in |

### D. Gas Analysis

| Part | What It Does |
|------|-------------|
| **CO2 Analyser** | Measures carbon dioxide in the exit gas. Tells you how actively the organisms are respiring |
| **O2 Analyser** | Measures oxygen in the exit gas. Combined with CO2 data, gives the Respiratory Quotient (RQ = CO2 produced / O2 consumed) |
| **Mass Spectrometer** | Gives a complete picture of all gases in the exhaust. More detailed but more expensive |

---

## How a Fermentation Run Happens (Step by Step)

1. **Sterilization** -- Steam at 121 deg C for 15-20 minutes kills everything inside
2. **Medium addition** -- Sterile growth medium is pumped in
3. **Inoculation** -- Starter culture of your microorganism is added through the inoculation port
4. **Growth phase** -- Motor starts, impellers mix the medium, air flows through the sparger, sensors monitor everything
5. **Control** -- Temperature, pH, dissolved oxygen, foam are all automatically maintained
6. **Sampling** -- Periodic samples are taken through the sample pipe to check growth and product formation
7. **Harvest** -- When fermentation is complete, the product is drained through the harvest line
8. **Cleaning** -- The fermenter is cleaned and sterilized for the next batch

---

## Viva Questions -- Experiment 1

### Basic Level

**Q1. What is a fermenter?**
A fermenter (bioreactor) is a sealed vessel designed for the controlled cultivation of microorganisms or cells for the production of biochemicals, enzymes, antibiotics, or other products through fermentation.

**Q2. What is the other name for a fermenter?**
Stirred Tank Reactor (STR) or Bioreactor.

**Q3. What material is the fermenter made of?**
Lab-scale fermenters are often made of borosilicate glass. Industrial fermenters are made of stainless steel (SS316 grade, which resists corrosion and can handle repeated steam sterilization).

**Q4. What are baffles and why are they needed?**
Baffles are 4 vertical metal strips (each about 1/10th of vessel diameter in width) attached to the inside wall. Without baffles, the impeller would just spin the liquid in a circle (creating a vortex). Baffles break this circular flow and create turbulence, which gives proper top-to-bottom mixing.

**Q5. What is a sparger?**
A sparger is a device at the bottom of the fermenter that introduces sterile air into the culture medium as fine bubbles. More surface area of bubbles means better oxygen transfer to the liquid.

**Q6. Why is the air filtered before entering the fermenter?**
To maintain sterility. Outside air contains bacteria, fungal spores, and dust particles. If these enter the fermenter, they will contaminate the culture and ruin the batch.

**Q7. Why do we need to control temperature during fermentation?**
Every microorganism has an optimal growth temperature. If the temperature goes too high, enzymes denature and the organism dies. If too low, metabolism slows down. Also, microbial metabolism itself generates heat, which can cause the temperature to rise uncontrollably without cooling.

**Q8. What is the function of the drive motor?**
The drive motor rotates the drive shaft and its attached impellers at a controlled speed (measured in RPM). This provides mixing, which ensures even distribution of nutrients, oxygen, heat, and pH throughout the medium.

---

### Intermediate Level

**Q9. What is the role of the cold water jacket?**
Microbial growth is exothermic -- it produces heat. If not removed, this heat would raise the temperature and kill the organisms or shift the metabolism. The cold water jacket circulates chilled water around the vessel to absorb this excess heat and maintain the set temperature.

**Q10. Why do we need a foam probe?**
During fermentation, vigorous agitation and the presence of proteins in the medium cause foam. Excessive foam can block the exhaust gas filter (leading to pressure build-up), wet the air filter (allowing contamination), or overflow from the vessel. The foam probe detects foam level and triggers the anti-foam pump.

**Q11. What is the difference between a peristaltic pump and a syringe pump?**
- Peristaltic pump: Squeezes a flexible tube in a rolling motion to push liquid. Runs continuously. Flow rate depends on tube size and roller speed. Good for continuous addition of medium, acids, bases, or anti-foam.
- Syringe pump: Pushes a syringe plunger at a precisely controlled rate. Very accurate for small volumes. Mainly used in batch operations.

**Q12. What is the Pt100 sensor? How does it work?**
Pt100 is a Platinum Resistance Thermometer. It has a platinum wire whose electrical resistance increases linearly with temperature. At 0 deg C, its resistance is exactly 100 ohms (that's why "Pt100"). By measuring the resistance, you calculate the temperature. It is very accurate and stable over time.

**Q13. Why is dissolved oxygen monitoring important?**
Aerobic microorganisms require oxygen for respiration and growth. If dissolved oxygen (DO) drops below a critical level, the organisms switch to anaerobic metabolism or simply stop growing. The DO probe lets the controller adjust agitation speed or air flow rate to maintain adequate oxygen levels.

**Q14. What is the purpose of exit gas analysis?**
By measuring CO2 produced and O2 consumed in the exhaust, you can calculate:
- Respiratory Quotient (RQ) = CO2 produced / O2 consumed
- Oxygen Uptake Rate (OUR)
- Carbon dioxide Evolution Rate (CER)
These tell you the metabolic state of the culture -- whether organisms are growing, producing product, or stressed.

**Q15. Why is sterility so important in fermentation?**
A contaminating organism can:
- Compete for nutrients and slow down the desired organism
- Produce toxic byproducts that kill your culture
- Produce unwanted chemicals that contaminate your product
- Change the pH or consume the product
One contamination event can destroy an entire batch worth lakhs of rupees in an industrial setting.

---

### Advanced Level

**Q16. What is the difference between a marine impeller and a Rushton turbine? When would you use each?**
- **Marine impeller**: Has 3 angled blades (like a ship propeller). Creates axial flow (pushes liquid from top to bottom). Low shear. Used for shear-sensitive cultures like animal cells, plant tissue culture, and filamentous fungi.
- **Rushton turbine**: Has 6 flat blades mounted on a central disc. Creates radial flow (pushes liquid outward from the centre). High shear. Great for breaking air bubbles into tiny ones (improving oxygen transfer). Used for bacterial fermentations.

**Q17. What is KLa and how does fermenter design affect it?**
KLa is the volumetric oxygen mass transfer coefficient (units: per hour). It describes how fast oxygen moves from air bubbles into the liquid medium.

KLa depends on:
- Impeller type and speed (higher speed = smaller bubbles = higher KLa)
- Sparger type (porous spargers give finer bubbles)
- Baffles (improve mixing and bubble dispersion)
- Air flow rate
- Medium viscosity (thick broths have lower KLa)
- Temperature

A well-designed fermenter maximizes KLa to ensure the culture never runs out of oxygen.

**Q18. How would you scale up a fermenter from 5L lab scale to 5000L industrial scale?**
You cannot simply build a bigger version. The key challenge is that as volume increases, surface-area-to-volume ratio decreases (making heat transfer harder) and mixing becomes non-uniform.

Common scale-up criteria (you pick one to keep constant):
- Constant power per unit volume (P/V) -- most common
- Constant impeller tip speed
- Constant KLa (oxygen transfer)
- Constant mixing time
- Constant Reynolds number

Geometric similarity is maintained (ratios of dimensions stay the same), but operating conditions (RPM, air flow) must be adjusted. No single criterion works perfectly; scale-up remains partly an art.

**Q19. What is the difference between batch, fed-batch, and continuous fermentation?**
- **Batch**: Everything is added at the start. Nothing added or removed during fermentation (except gases and samples). Simple. Product harvested at the end.
- **Fed-batch**: Like batch, but you slowly add more nutrients during fermentation. Avoids substrate inhibition. Most common in industry (e.g., penicillin production).
- **Continuous**: Fresh medium is continuously added and spent medium (with product) is continuously removed. Organism stays in steady state. Used for ethanol, single-cell protein production.

**Q20. What is CIP and SIP in fermentation?**
- **CIP (Clean In Place)**: The fermenter is cleaned without disassembly by circulating cleaning solutions (NaOH, acid, water) through all pipes and the vessel.
- **SIP (Sterilize In Place)**: Steam at 121 deg C is passed through the entire system to kill all microorganisms before starting a new batch.

Both reduce turnaround time and contamination risk.

---
---

# EXPERIMENT 2: DETERMINATION OF ENZYMATIC ACTIVITY OF AMYLASE

## Aim
To determine the total enzyme activity and specific enzyme activity of amylase using the DNS (3,5-Dinitrosalicylic acid) assay and Lowry's protein estimation method.

---

## Detailed Explanation in Simple Words

### What is Amylase?
Amylase is an enzyme found in your saliva, pancreas, and produced by many microorganisms. Its job is to break down starch. Starch is a long chain of glucose molecules linked together. Amylase cuts this chain into smaller pieces.

There are different types:
- **Alpha-amylase** -- cuts the chain randomly in the middle (endo-acting). Produces a mix of maltose, glucose, and short chains (dextrins)
- **Beta-amylase** -- cuts from the ends, producing only maltose (exo-acting)
- **Glucoamylase** -- cuts from the ends but releases single glucose units

In this experiment, alpha-amylase was used.

### Starch Structure (What Amylase Cuts)

Starch has two components:
1. **Amylose** (~20-30%): A straight chain of glucose units connected by alpha-1,4 bonds. Like a string of beads in a line.
2. **Amylopectin** (~70-80%): A branched chain. Has alpha-1,4 bonds in the straight parts and alpha-1,6 bonds at the branch points. Like a tree with branches.

Alpha-amylase cuts the alpha-1,4 bonds. It cannot cut the alpha-1,6 branch points.

### What is Enzyme Activity?

Enzyme activity tells you "how fast is this enzyme working?"

**One Unit of enzyme activity** = the amount of enzyme that produces 1 micromole of product (reducing sugar/maltose) per minute under specified conditions (temperature, pH, substrate concentration).

**Formula:**
```
Enzyme Activity = micromoles of maltose formed / (incubation time in minutes x volume of enzyme in ml)
```

### What is Specific Activity?

Specific activity tells you "how pure is this enzyme?"

```
Specific Activity = Enzyme Activity / Amount of protein (mg)
                  = micromoles of product / (time x mg of protein)
```

If your enzyme sample is crude (contains lots of other proteins), specific activity will be low. If purified (mostly enzyme), specific activity will be high. So it's a measure of purity.

### How Was Enzyme Activity Measured? -- The DNS Method

**The idea:** Amylase breaks starch into maltose. Maltose is a "reducing sugar" -- it has a free aldehyde group that can donate electrons. DNS reagent accepts these electrons and changes colour.

**Step by step:**

1. **Set up the reaction**: Mixed 0.5 ml of diluted starch solution + 0.5 ml of enzyme (amylase) in a tube
2. **Let it react**: Incubated for 10 minutes at room temperature. During this time, amylase chops starch into maltose
3. **Stop the reaction**: Added 1 ml of DNS reagent. This also kills the enzyme (the alkaline conditions denature it)
4. **Develop colour**: Boiled in a water bath for 5 minutes. Heat + alkaline conditions drive the reaction between DNS and maltose. The pale yellow DNS turns orange-red
5. **Stabilize colour**: Added 1 ml of 40% Rochelle salt (sodium potassium tartarate). This stabilizes the colour so it doesn't fade
6. **Measure**: Read the absorbance at 540 nm against a blank (same procedure but buffer instead of enzyme)

**Why 540 nm?** The orange-red product (3-amino-5-nitrosalicylic acid) absorbs light most strongly at 540 nm. That's its absorption maximum.

**Why boil for 5 minutes?** The DNS reaction needs heat to proceed. Boiling ensures the reaction goes to completion so you get full colour development.

**Why Rochelle salt?** Without it, the colour fades within minutes, making accurate measurement impossible.

### The Maltose Standard Curve

Before you can find out how much maltose your enzyme produced, you need a reference. You make solutions of known maltose concentrations (0.1, 0.2, 0.3, 0.4, 0.5 mg/ml), run the same DNS procedure on each, and plot a graph:

- X-axis: maltose concentration (mg/ml)
- Y-axis: absorbance at 540 nm

This gives a straight line. The equation from the experiment was: **y = 1.8631x + 0.1505** (R-squared = 0.9228)

Now when you get an absorbance reading from your unknown sample, you plug it into this equation and solve for x to get the maltose concentration.

### How Was Protein Measured? -- Lowry's Method

To calculate specific activity, you need to know how much total protein is in your enzyme sample.

**Lowry's method** is one of the oldest and most used protein estimation methods. It works in two steps:

**Step 1 -- Biuret Reaction:**
- Proteins have peptide bonds (-CO-NH-)
- Under alkaline conditions, copper ions (Cu2+) bind to these peptide bonds
- This forms a copper-protein complex (purple/violet colour)

**Step 2 -- Folin Reaction:**
- The copper-protein complex reduces the Folin-Ciocalteu reagent (phosphomolybdic + phosphotungstic acid)
- This produces a deep blue colour
- The intensity of blue is proportional to the amount of protein

**Measurement**: Absorbance at 660 nm against a blank.

**Reagents for Lowry's method:**
- Reagent A: 2% Na2CO3 in 0.1N NaOH
- Reagent B: 1% NaK Tartarate in H2O
- Reagent C: 0.5% CuSO4.5H2O in H2O
- Reagent I: 48 ml of A + 1 ml of B + 1 ml of C
- Reagent II: Folin-Ciocalteu phenol reagent (2N) diluted 1:1 with water

### BSA Standard Curve

Just like the maltose standard curve, you make a protein standard curve using **BSA (Bovine Serum Albumin)** at known concentrations (0.1, 0.2, 0.4, 0.6, 0.8, 1.0 mg/ml).

Equation from experiment: **y = 0.8992x + 0.0732** (R-squared = 0.9693)

### Putting It All Together -- The Calculations

**Step 1: Find maltose produced**
- DNS assay absorbance for replicate 1 = 0.882, replicate 2 = 0.784
- From maltose standard curve: concentration for Rep 1 = 0.388 mg/ml, Rep 2 = 0.344 mg/ml
- Average = (0.388 + 0.344) / 2 = **0.366 mg/ml**

**Step 2: Convert to micromoles**
- Molecular weight of maltose = 342.3 g/mol = 342.3 x 10^3 mg/mol
- Moles = 0.366 mg/ml / (342.3 x 10^3 mg/mol) = 0.000001070 mol/ml = **1.0701 micromoles/ml**

**Step 3: Account for reaction volume**
- Total reaction volume = 0.5 ml substrate + 0.5 ml enzyme = 1 ml
- Moles of maltose produced = 1.0701 micromoles/ml x 1 ml = **1.0701 micromoles**

**Step 4: Calculate enzyme activity**
```
Enzyme Activity = micromoles of maltose / (incubation time x volume of enzyme)
                = 1.0701 / (10 min x 0.5 ml)
                = 0.21402 micromoles/min/ml
```

**Step 5: Find protein amount (from Lowry)**
- Absorbance at 660 nm for enzyme sample = 0.133
- From BSA standard curve: protein concentration for Rep 1 = 0.1346 mg, Rep 2 = 0.1326 mg
- Average = **0.1336 mg**

**Step 6: Calculate specific activity**
```
Specific Activity = micromoles of maltose / (time x protein)
                  = 1.0701 / (10 min x 0.1336 mg)
                  = 0.80097 micromoles/min/mg
```

### Results Summary

| Parameter | Value |
|-----------|-------|
| Maltose produced | 0.366 mg/ml |
| Enzyme activity | 0.21402 umol/min/ml |
| Protein content | 0.1336 mg |
| Specific enzyme activity | 0.80097 umol/min/mg |

---

## Viva Questions -- Experiment 2

### Basic Level

**Q1. What is amylase?**
Amylase is a hydrolytic enzyme that breaks down starch (a polysaccharide) into smaller sugars, mainly maltose and glucose. It hydrolyses the alpha-1,4 glycosidic bonds in starch.

**Q2. Where is amylase found in the human body?**
In saliva (salivary amylase or ptyalin) and in pancreatic juice (pancreatic amylase). Salivary amylase starts starch digestion in the mouth; pancreatic amylase continues it in the small intestine.

**Q3. What is enzyme activity?**
Enzyme activity is the rate at which an enzyme converts substrate to product. One unit of enzyme activity is defined as the amount of enzyme that liberates 1 micromole of reducing sugar (product) per minute under specified assay conditions.

**Q4. What is the DNS method?**
The DNS (3,5-Dinitrosalicylic Acid) method is a colorimetric assay for detecting reducing sugars. DNS (yellow) reacts with reducing sugars under alkaline, hot conditions and gets reduced to 3-amino-5-nitrosalicylic acid (orange-red). The colour intensity is proportional to the sugar concentration.

**Q5. At what wavelength is the DNS assay read?**
540 nm. This is the absorption maximum of the orange-red product.

**Q6. What is a reducing sugar? Give examples.**
A reducing sugar has a free anomeric carbon (free aldehyde or ketone group) that can act as a reducing agent. Examples: glucose, maltose, fructose, lactose. Sucrose is NOT a reducing sugar because both anomeric carbons are locked in the glycosidic bond.

**Q7. What is a standard curve and why do you need one?**
A standard curve is a graph plotted using known concentrations of a substance (like maltose) versus their measured absorbance. It acts as a reference. When you have an unknown sample, you measure its absorbance, find that value on the standard curve, and read off the concentration.

**Q8. Why is Rochelle salt added after boiling?**
Rochelle salt (sodium potassium tartarate) stabilizes the colour produced by the DNS reaction. Without it, the orange-red colour fades rapidly, giving inaccurate readings.

---

### Intermediate Level

**Q9. What is specific enzyme activity? Why is it important?**
Specific activity = enzyme activity per milligram of total protein (units: umol/min/mg). It reflects the purity of the enzyme preparation. During enzyme purification, you track specific activity -- it should increase with each purification step because you are removing non-enzyme proteins.

**Q10. What is Lowry's method? How does it work?**
Lowry's method estimates total protein concentration. It works in two stages:
1. Biuret reaction -- Copper ions bind to peptide bonds in alkaline conditions
2. Folin reduction -- The copper-protein complex reduces Folin-Ciocalteu reagent to produce a blue colour
Measured at 660 nm. Sensitive to about 10 ug/ml.

**Q11. Why is BSA used as the standard for protein estimation?**
BSA (Bovine Serum Albumin) is cheap, stable, well-characterised, highly pure, and readily available. It gives a reproducible colour response with Lowry reagent and is the internationally accepted reference standard.

**Q12. What is the difference between total activity and specific activity?**
- Total activity = total units of enzyme in the entire sample. Tells you "how much enzyme do I have in total?"
- Specific activity = units per mg of protein. Tells you "how pure is my enzyme?"
During purification, total activity may decrease (you lose some enzyme), but specific activity should increase (you lose more non-enzyme protein).

**Q13. Why do we boil the DNS reaction for exactly 5 minutes?**
Boiling provides the energy needed for the DNS reduction reaction to go to completion. Too short = incomplete colour development (underestimates sugar). Too long = sugar can degrade or side reactions occur. Five minutes is the standardized time that gives consistent results.

**Q14. What is the purpose of the blank in this experiment?**
The blank contains buffer instead of enzyme, with everything else the same. It corrects for any background colour from the reagents, starch, or DNS. You measure samples "against the blank" so that only the colour from enzyme-produced maltose is measured.

**Q15. Why was the reaction incubated for 10 minutes specifically?**
This is a standardized assay time. It is short enough that the reaction is still in the initial rate phase (substrate is not significantly depleted) but long enough to produce measurable amounts of maltose.

**Q16. Why multiply by 2 (x2) in the enzyme activity calculation?**
Because only 0.5 ml of enzyme was used in the reaction, but enzyme activity is reported per 1 ml. So you multiply by 2 to normalize to 1 ml of enzyme solution. The formula accounts for this: Activity = umoles / (time x volume of enzyme).

---

### Advanced Level

**Q17. What are the limitations of Lowry's method?**
- Interfered by: Tris buffer, EDTA, non-ionic detergents (Triton X-100), cationic detergents, carbohydrates, lipids, urea, and some salts
- It is a relative method -- assumes all proteins react like BSA, which isn't true (aromatic amino acid content varies)
- Requires strict timing
- Not suitable for membrane proteins dissolved in detergent
- Slow (takes about 1 hour)

**Q18. What are the alternatives to Lowry's method for protein estimation?**
- **Bradford method** -- Uses Coomassie Brilliant Blue dye. Faster (5 min), less prone to interference, but more variable between different proteins
- **BCA method** -- Bicinchoninic acid method. More tolerant of detergents than Lowry
- **UV absorbance at 280 nm** -- Quick and non-destructive but affected by nucleic acids
- **Kjeldahl method** -- Measures total nitrogen. Very accurate but slow and destructive

**Q19. Starch is not a reducing sugar. Then how does the DNS assay work in this experiment?**
Correct -- intact starch is not a reducing sugar. But amylase breaks starch into maltose, which IS a reducing sugar. The DNS reagent detects the maltose produced by the enzyme. The blank (no enzyme) produces no maltose and thus no colour change, confirming that the colour is from enzymatic action.

**Q20. How would you modify this assay to measure amylase activity in a sample that also contains glucose oxidase?**
Glucose oxidase would convert any free glucose (produced from starch) into gluconic acid and H2O2. This would reduce the amount of reducing sugar detected by DNS. You could:
- Add a glucose oxidase inhibitor
- Use a specific maltose detection method instead of the non-specific DNS method
- Heat-inactivate the glucose oxidase before the DNS step

**Q21. What is the molar extinction coefficient, and how does it relate to this experiment?**
The molar extinction coefficient (epsilon) relates absorbance to concentration through Beer-Lambert law: A = epsilon x c x l (where A = absorbance, c = concentration in mol/L, l = path length in cm). In this experiment, rather than using the extinction coefficient directly, we use a standard curve to empirically relate absorbance to concentration.

**Q22. If you accidentally used a 10x more concentrated enzyme, what would happen?**
Much more maltose would be produced, potentially exceeding the linear range of the DNS assay (OD > 1.0). The Beer-Lambert law breaks down at high absorbance. You would need to dilute your enzyme and repeat the assay.

---
---

# EXPERIMENT 3: DETERMINATION OF KINETIC CONSTANTS (Km AND Vmax) OF AMYLASE-CATALYZED STARCH HYDROLYSIS

## Aim
To determine the Michaelis-Menten kinetic constants Km and Vmax of free amylase-catalyzed starch hydrolysis under specified conditions, using the Lineweaver-Burk double reciprocal plot.

---

## Detailed Explanation in Simple Words

### The Core Idea

Every enzyme has a speed limit. No matter how much substrate you throw at it, there is a maximum speed (Vmax) it can never exceed. This experiment is about measuring that speed limit and understanding how well the enzyme grabs its substrate.

### The Michaelis-Menten Model -- A Story

Imagine a factory worker (the enzyme) assembling toys (the product) from parts (the substrate).

1. When only a few parts are on the table, the worker picks up one, assembles it, then looks for the next. The bottleneck is finding parts. More parts = faster output. **This is the low substrate region** -- reaction rate increases almost linearly with substrate concentration (first-order kinetics).

2. As you pile more and more parts on the table, the worker is always busy -- as soon as they finish one toy, they immediately grab the next part. Adding even more parts doesn't help because the worker is already going full speed. **This is the high substrate region** -- the enzyme is saturated, and the rate plateaus at Vmax (zero-order kinetics).

3. **Km** is the amount of parts on the table where the worker is going at exactly half their maximum speed. A small Km means the worker is so eager that even a few parts keep them busy (high affinity). A large Km means the worker is picky and needs lots of parts around to stay occupied (low affinity).

### The Michaelis-Menten Equation

```
        Vmax x [S]
V = ----------------
        Km + [S]
```

Where:
- V = reaction velocity (rate) at a given substrate concentration
- Vmax = maximum velocity when enzyme is fully saturated
- [S] = substrate concentration
- Km = Michaelis constant (substrate concentration at which V = Vmax/2)

### The Problem with a Curved Graph

If you plot V vs [S], you get a hyperbolic curve (like a curve that rises steeply then flattens out). The problem is:
- Vmax is the plateau, but the curve approaches it asymptotically -- it never quite reaches it, so you can't read an exact value
- Km is somewhere in the middle of the curve and hard to pinpoint

### The Solution -- Lineweaver-Burk Plot (Double Reciprocal)

Take the reciprocal of both sides of the Michaelis-Menten equation:

```
1       Km        1        1
--- = ------- x ----- + ------
V     Vmax      [S]     Vmax
```

This is in the form y = mx + c (a straight line equation!) where:
- y = 1/V
- x = 1/[S]
- Slope (m) = Km/Vmax
- Y-intercept (c) = 1/Vmax
- X-intercept = -1/Km

Now you just need to plot 1/V vs 1/[S], draw the best-fit line, and read off the values.

### What Was Actually Done in the Lab

**Step 1 -- Prepare different substrate concentrations:**
Made starch solutions at 0.03%, 0.05%, 0.07%, 0.08%, and 0.1% (w/v) in phosphate buffer (pH 7).

**Step 2 -- Set up reactions:**
For each starch concentration: mixed 9 ml starch + 9 ml enzyme solution. Incubated at 37 degrees C.

**Step 3 -- Take time samples:**
Every 2 minutes (0, 2, 4, 6, 8, 10 min), withdrew 1 ml of the reaction mixture.

**Step 4 -- DNS assay on each sample:**
Added 1 ml DNS to each sample, boiled 5 min, added Rochelle salt, measured absorbance at 540 nm against analytical blank.

**Step 5 -- Calculate maltose at each time point:**
Used the maltose standard curve to convert absorbance to maltose concentration (mg/ml), then to mM.

**Step 6 -- Plot P vs t (product vs time):**
For each starch concentration, plotted maltose produced (mM) vs time (min). Got a curve.

**Step 7 -- Find initial rate (V0):**
The initial rate is the slope of the P vs t curve at time = 0. Fitted a polynomial, took the derivative at t = 0. This gives V0 in mM/min.

For 0.07% starch, the equation was y = -0.0045x^2 + 0.1557x. At x = 0, slope = 0.1557 mM/L/min.

**Step 8 -- Make the Lineweaver-Burk plot:**
Calculated 1/[S] and 1/V0 for each starch concentration. Plotted 1/V0 vs 1/[S]. Got a straight line.

### Results from the Experiment

**Lineweaver-Burk equation:** y = 13.75x + 1.8563 (R-squared = 0.9996, excellent fit)

| Starch % (w/v) | [S] (mM) | V0 (mmol/L/min) | 1/[S] | 1/V0 |
|-----------------|-----------|-----------------|-------|------|
| 0.03 | 3 x 10^-5 | 0.1552 | 0.35 | 6.443 |
| 0.05 | 5 x 10^-5 | 0.1385 | 0.21 | 7.220 |
| 0.07 | 7 x 10^-5 | 0.1557 | 0.15 | 6.423 |
| 0.08 | 8 x 10^-5 | 0.2825 | 0.13 | 3.54 |
| 0.1 | 10 x 10^-5 | 0.3065 | 0.105 | 3.263 |

**Calculated values:**
- Y-intercept = 1/Vmax = 1.8563 --> **Vmax = 0.5387 mM/L/min**
- Slope = Km/Vmax = 13.75 --> **Km = 13.75 x 0.5387 = 7.41 x 10^-5 mM**

### What Do These Numbers Mean?

- **Vmax = 0.5387 mM/min**: At full saturation, amylase can produce maltose at a rate of 0.5387 millimoles per litre per minute. This is the fastest it can go.
- **Km = 7.41 x 10^-5 mM**: This is an extremely small Km, meaning the enzyme has very high affinity for starch. It reaches half its top speed at a very tiny starch concentration.

### Why Use Initial Rate?

If you measure the rate later in the reaction:
- Substrate is getting used up (so the concentration you started with is no longer accurate)
- Product (maltose) is accumulating and might inhibit the enzyme (product inhibition)
- The reaction might even reverse slightly

Initial rate avoids all these problems. At t = 0, the substrate concentration is exactly what you set, and no product has accumulated yet.

### Two Types of Blanks

1. **Zero substrate blank (0% starch)**: Buffer + enzyme, no starch. This tells you the rate at zero substrate concentration and serves as a data point on the Lineweaver-Burk plot.

2. **Analytical blank**: Starch + buffer, no enzyme. This corrects for background absorbance from the starch, buffer, and DNS reagent. You need one for each starch concentration.

---

## Viva Questions -- Experiment 3

### Basic Level

**Q1. What is Km (Michaelis constant)?**
Km is the substrate concentration at which the enzyme operates at half of its maximum velocity (Vmax/2). It's a measure of the enzyme's affinity for its substrate. Lower Km = higher affinity.

**Q2. What is Vmax?**
Vmax is the maximum reaction velocity achieved when every enzyme molecule in the solution has its active site occupied by substrate. Adding more substrate beyond this point does not increase the rate.

**Q3. Write the Michaelis-Menten equation.**
V = Vmax[S] / (Km + [S]), where V is reaction velocity, [S] is substrate concentration, Vmax is maximum velocity, and Km is the Michaelis constant.

**Q4. What is a Lineweaver-Burk plot?**
A double reciprocal plot where 1/V (y-axis) is plotted against 1/[S] (x-axis). It linearizes the Michaelis-Menten equation into 1/V = (Km/Vmax)(1/[S]) + 1/Vmax.

**Q5. Why not just read Km and Vmax from the V vs [S] curve directly?**
The V vs [S] curve is a hyperbola that approaches Vmax asymptotically -- it never actually reaches it. So you cannot get an accurate Vmax value. Similarly, Km (at Vmax/2) can't be precisely determined from a curve. The Lineweaver-Burk plot converts this to a straight line where exact values can be read from intercepts.

**Q6. What is the initial rate of a reaction?**
The reaction rate measured at the very beginning of the reaction (time approaching zero), before the substrate has been significantly consumed or product has accumulated. It is found by taking the slope of the product-vs-time curve at t = 0.

**Q7. What does it mean if the enzyme follows first-order kinetics?**
The rate is directly proportional to substrate concentration. Doubling [S] doubles the rate. This happens when [S] is much less than Km (most enzyme molecules are free, not bound to substrate).

**Q8. What does it mean if the enzyme follows zero-order kinetics?**
The rate does not change with substrate concentration. This happens when [S] is much greater than Km (enzyme is saturated). Adding more substrate has no effect.

---

### Intermediate Level

**Q9. How do you extract Km, Vmax, and other parameters from the Lineweaver-Burk plot?**
- Y-intercept = 1/Vmax --> Vmax = 1/(y-intercept)
- X-intercept = -1/Km --> Km = -1/(x-intercept)
- Slope = Km/Vmax

**Q10. What is the steady-state assumption?**
The Michaelis-Menten derivation assumes that the enzyme-substrate complex (ES) concentration remains constant over time -- the rate of ES formation equals the rate of ES breakdown. This holds when [S] >> [E] (substrate is in large excess over enzyme).

**Q11. What is an enzyme-substrate complex?**
When enzyme (E) meets substrate (S), they bind together at the active site to form a temporary ES complex. This complex then either breaks back into E + S or proceeds forward to give product (P) and regenerate the free enzyme: E + S <--> ES --> P + E.

**Q12. Why were multiple starch concentrations used?**
Each concentration gives one data point (one V0 value). You need multiple points to see how V changes with [S] and to draw the Lineweaver-Burk line. More points = better accuracy.

**Q13. Why incubate at 37 degrees C?**
This is near the optimal temperature for most amylases. Enzyme activity increases with temperature (up to the optimum) because molecules move faster and collide more often. Beyond the optimum, the enzyme starts to denature.

**Q14. Why use phosphate buffer at pH 7?**
Amylase works best at neutral to slightly alkaline pH. The buffer maintains pH at 7 throughout the reaction, preventing pH drift that would alter enzyme activity and give misleading kinetic data.

**Q15. What happens to Km and Vmax in the presence of a competitive inhibitor?**
Competitive inhibitors bind to the active site (competing with substrate). Km increases (apparent lower affinity) because you need more substrate to overcome the inhibitor. Vmax stays the same because at very high [S], substrate outcompetes the inhibitor.

**Q16. What happens to Km and Vmax with a non-competitive inhibitor?**
Non-competitive inhibitors bind away from the active site and reduce the enzyme's catalytic ability. Km stays the same (substrate binding is unaffected) but Vmax decreases (some enzyme molecules are permanently disabled).

---

### Advanced Level

**Q17. What are the limitations of the Lineweaver-Burk plot?**
1. **Distorts errors**: Low [S] values (which inherently have more experimental error) produce very large 1/[S] values that dominate the graph and the regression line
2. **Clusters high [S] data near the y-axis**: The most reliable data points get compressed near the origin
3. **Extrapolation issues**: The line must be extended far to find -1/Km on the x-axis

Better alternatives: Eadie-Hofstee plot (V vs V/[S]) or Hanes-Woolf plot ([S]/V vs [S]). Even better: non-linear regression fitting directly to the Michaelis-Menten equation using software.

**Q18. What is the turnover number (kcat)?**
kcat = Vmax / [E]total, where [E]total is the total enzyme concentration. It represents the number of substrate molecules converted to product per enzyme molecule per unit time (per second). A higher kcat means a faster enzyme.

**Q19. What is catalytic efficiency?**
Catalytic efficiency = kcat / Km. It combines the enzyme's speed (kcat) and affinity (Km) into one number. The theoretical maximum is limited by diffusion (~10^8 to 10^9 M^-1 s^-1). Enzymes that reach this limit are called "catalytically perfect" (e.g., carbonic anhydrase, catalase).

**Q20. How would you determine if the enzyme shows substrate inhibition?**
In substrate inhibition, excess substrate actually slows the enzyme down (perhaps by binding to a second, inhibitory site). The V vs [S] curve rises, reaches a peak, then drops. The Lineweaver-Burk plot curves upward at low 1/[S] (high [S]) instead of being straight. You would need to modify the kinetic model.

**Q21. What is the difference between Michaelis-Menten and Hill kinetics?**
Michaelis-Menten applies to simple enzymes with one substrate binding site. Hill kinetics applies to cooperative enzymes (like hemoglobin) where binding of one substrate molecule affects the binding of subsequent molecules. The Hill equation includes a Hill coefficient (n): n > 1 means positive cooperativity, n < 1 means negative cooperativity, n = 1 reduces to Michaelis-Menten.

**Q22. In this experiment, Km was found to be 7.41 x 10^-5 mM. Is this reasonable for amylase?**
This is extremely low. Literature values for alpha-amylase Km with starch typically range from 0.1 to 5 mg/ml (roughly 0.3 to 15 mM). The very low Km found here may be because: the starch was already quite dilute (concentrations in w/v% were converted to mM using a very large molecular weight for starch), or because the alpha-amylase used has very high affinity for this particular starch preparation.

---
---

# EXPERIMENT 4: DETERMINATION OF KINETIC CONSTANTS Km AND Vmax OF IMMOBILIZED ENZYMES (CALCIUM ALGINATE ENTRAPMENT)

## Aim
To determine the kinetic constants Km and Vmax of immobilized amylase enzyme (entrapped in calcium alginate beads) catalyzed starch hydrolysis under specified conditions, and to compare with free enzyme kinetics.

---

## Detailed Explanation in Simple Words

### Why Immobilize an Enzyme?

Free enzymes in solution are like loose workers in a factory -- they do their job, but at the end of the day, they get mixed into the product and you can't easily separate or reuse them.

Immobilized enzymes are like workers chained to their workstations. They stay in place, do their job, and when the product flows out, the workers are still there ready for the next batch.

**Benefits of immobilization:**
1. **Reusability** -- Use the same enzyme over and over (huge cost savings)
2. **Easy separation** -- Just filter out the beads; enzyme doesn't contaminate the product
3. **Continuous operation** -- Pack beads in a column, flow substrate through, product comes out the other end
4. **Better stability** -- Immobilized enzymes often resist heat and pH changes better than free enzymes
5. **Controlled reaction** -- Can stop the reaction instantly by removing the beads

**Drawbacks:**
1. **Reduced activity** -- Diffusion limitations slow things down
2. **Mass transfer resistance** -- Substrate has to diffuse into the bead, product has to diffuse out
3. **Enzyme loss** -- Some enzyme leaks out during washing or operation
4. **Cost** -- The immobilization materials and process add cost

### How Calcium Alginate Beads Were Made

**Sodium alginate** is a natural polysaccharide extracted from brown seaweed. In water, it forms a thick, gooey solution (like a thick syrup).

When you add **calcium chloride (CaCl2)**, the calcium ions (Ca2+) cross-link the alginate chains. Each Ca2+ ion bridges two alginate chains, creating a solid gel network. This is called **ionic gelation**.

The process:
1. Dissolved 3 gm sodium alginate in 100 ml water (3% solution) -- makes a thick liquid
2. Mixed 70 mg of amylase enzyme into this alginate solution
3. Using a peristaltic pump (at 4 rpm) and a capillary tube, dropped this enzyme-alginate mixture into a beaker containing 3% CaCl2 solution
4. Each drop instantly gelled on contact with calcium, forming a small round bead
5. The enzyme molecules get physically trapped inside the gel network
6. Left the beads in CaCl2 for some time to harden completely
7. Washed the beads 2-3 times with phosphate buffer to remove loose (untrapped) enzyme

### Characterization of the Beads

**Bead diameter**: Measured by displacement method
- 100 beads displaced 8 ml of liquid = 8000 mm^3
- Volume of 1 bead = 80 mm^3
- Using V = (4/3)pi*r^3: radius = 2.67 mm, so diameter = **5.34 mm**

**Total beads made**: 
- 100 beads displaced 8 ml
- Total liquid displaced by all beads = 100 ml
- Total beads = (100/8) x 100 = **1250 beads**

**Enzyme loading and loss:**
- Enzyme loaded = 70 mg total
- Washed the beads, collected wash water, measured protein by Lowry's method
- Wash water had 0.07185 mg/ml protein x 100 ml = **7.185 mg lost**
- Enzyme retained = 70 - 7.185 = **62.815 mg**
- Enzyme per bead = 62.815 / 1250 = **0.0502 mg/bead**
- For experiments, used 5 beads (~0.25 mg enzyme per reaction)

**Blank beads**: Made the same way but without enzyme. Used as controls.

### How Km and Vmax Were Measured

Same approach as Experiment 3 but with beads instead of free enzyme:

1. Prepared starch solutions at two concentrations: 0.015% and 0.02% (w/v) in phosphate buffer
2. Added 5 enzyme beads + 1 ml starch solution in each tube (duplicates for each condition)
3. Also set up blanks with 5 blank beads (no enzyme) + starch
4. Incubated at room temperature
5. Withdrew 500 ul samples at 0, 3, 6, 9, and 12 minutes
6. Performed DNS assay on each sample
7. Calculated maltose concentration at each time point
8. Plotted maltose (mM) vs time (min) for each starch concentration
9. Found initial rate (V0) from the slope at t = 0
10. Made Lineweaver-Burk plot using data from multiple starch concentrations

### Results

**For 0.015% starch:** V0 = 0.0441 mM/min (from graph slope)
**For 0.020% starch:** V0 = 0.0652 mM/min

**Lineweaver-Burk plot equation:** y = 17.928x + 10.722 (R-squared = 0.9991)

| Parameter | Value |
|-----------|-------|
| 1/Vmax (y-intercept) | 10.722 |
| **Vmax** | **0.093 mM/min = 0.093 umoles/ml/min** |
| Slope (Km/Vmax) | 17.928 |
| **Km** | **17.928 x 0.093 = 1.672 x 10^-5 umoles/ml** |

### Comparison with Free Enzyme (Experiment 3)

| Parameter | Free Enzyme (Exp 3) | Immobilized Enzyme (Exp 4) |
|-----------|--------------------|-----------------------------|
| Vmax | 0.5387 mM/min | 0.093 mM/min |
| Km | 7.41 x 10^-5 mM | 1.672 x 10^-5 umoles/ml |

**Both Km and Vmax decreased after immobilization.** This is because of **diffusion limitations** -- the substrate (starch) has to travel through the alginate gel to reach the trapped enzyme, and the product (maltose) has to travel back out.

### Why Does Vmax Decrease?

The gel creates a physical barrier. Even when you flood the system with substrate, the enzyme molecules deep inside the bead don't get as much substrate as they would if floating freely. So the effective maximum rate is lower.

### Why Does Km Change?

The apparent Km can either increase or decrease depending on the immobilization method:
- **Increases** if external diffusion limitation dominates (substrate can't reach the enzyme fast enough)
- **Decreases** if partitioning effects concentrate the substrate near the enzyme (can happen with charged supports)

In this experiment, Km decreased, suggesting that the alginate matrix may have some concentrating effect on starch near the enzyme.

---

## Viva Questions -- Experiment 4

### Basic Level

**Q1. What is enzyme immobilization?**
It is the technique of fixing or confining an enzyme onto or within a solid support (matrix) so that the enzyme retains its catalytic activity but cannot move freely in solution. This allows the enzyme to be recovered and reused.

**Q2. Name the main methods of enzyme immobilization.**
1. **Adsorption** -- Enzyme sticks to a surface via weak forces (van der Waals, hydrophobic, ionic interactions)
2. **Covalent binding** -- Enzyme is chemically bonded to the support via functional groups
3. **Entrapment** -- Enzyme is trapped inside a polymer gel or fibre matrix (like alginate beads)
4. **Cross-linking** -- Enzyme molecules are linked to each other by a cross-linking agent (like glutaraldehyde)
5. **Encapsulation** -- Enzyme is enclosed within a semi-permeable membrane

**Q3. What is calcium alginate?**
It is a gel formed when sodium alginate (a polymer from seaweed) is mixed with calcium chloride solution. The Ca2+ ions cross-link the alginate polymer chains into a solid, porous gel through ionic interactions.

**Q4. Why immobilize enzymes?**
Main reasons: Reusability (major cost saving), easy separation from product, ability to use in continuous reactors, often improved stability against temperature and pH changes.

**Q5. How were the alginate beads prepared?**
Mixed 70 mg amylase with 100 ml of 3% sodium alginate solution. Dropped this mixture through a capillary tube (using a peristaltic pump at 4 rpm) into 3% CaCl2 solution. Each drop solidified into a bead on contact with calcium.

**Q6. Why were the beads washed?**
To remove enzyme that was loosely adsorbed on the bead surface rather than trapped inside. Surface enzyme would give falsely high initial activity readings and would fall off during use.

---

### Intermediate Level

**Q7. Why did Vmax decrease for the immobilized enzyme?**
Diffusion limitation. The starch molecules must diffuse through the porous alginate gel to reach the enzyme inside the bead. This creates a mass transfer resistance. Even at saturating substrate concentrations, the enzyme deep inside the bead doesn't "see" the full external concentration. So the effective maximum rate drops.

**Q8. What is the difference between external and internal diffusion limitations?**
- **External (film) diffusion**: Around every bead in solution, there is a stagnant liquid layer (boundary layer). Substrate must diffuse through this layer to reach the bead surface. Can be reduced by increasing agitation.
- **Internal (pore) diffusion**: Once at the bead surface, substrate must diffuse through the gel pores to reach enzyme molecules inside. Can be reduced by making smaller beads or more porous gels.

**Q9. How could you reduce diffusion limitations?**
- Use smaller beads (shorter diffusion path)
- Lower alginate concentration (more porous gel)
- Increase stirring/agitation (reduces external film thickness)
- Use higher substrate concentrations
- Increase temperature slightly (faster diffusion, but don't denature the enzyme)

**Q10. How was the enzyme loss during immobilization calculated?**
Collected the wash water after washing the beads. Measured the protein concentration in this wash using Lowry's method. Multiplied by total wash volume to get total protein lost. This represents enzyme that failed to get trapped inside the beads.

**Q11. What are blank beads and why are they needed?**
Blank beads are alginate beads made without enzyme (just alginate + CaCl2). They are used as controls in the DNS assay to correct for any background colour or absorbance caused by the alginate gel itself or any compounds leaching from it.

**Q12. How was bead diameter measured?**
By displacement method. Counted 100 beads. Placed them in a measuring cylinder with known liquid volume. The liquid level rose by 8 ml. So 100 beads = 8 ml = 8000 mm^3. One bead = 80 mm^3. Using V = (4/3)(pi)(r^3), calculated r = 2.67 mm, diameter = 5.34 mm.

**Q13. What factors affect the size of alginate beads?**
- Capillary tube diameter (wider tube = bigger drops = bigger beads)
- Flow rate from the pump (faster flow = bigger drops)
- Height from which drops fall (higher drop = more elongation before hitting CaCl2)
- Alginate concentration (thicker solution = bigger drops that don't pinch off easily)
- Needle gauge if using a needle instead of capillary

---

### Advanced Level

**Q14. What would happen if you used 1% alginate instead of 3%?**
The beads would be softer, more fragile, and more porous. More enzyme would leak out (lower entrapment efficiency). However, diffusion would be easier due to larger pore sizes, so the Vmax might be closer to the free enzyme value. There's always a trade-off between mechanical strength and diffusion.

**Q15. Can alginate beads be used in organic solvents?**
Alginate beads are hydrophilic and swell in water. In organic solvents, they would shrink and possibly crack. For non-aqueous enzymology, other supports like silica, chitosan cross-linked with glutaraldehyde, or synthetic polymers are better.

**Q16. What is the effectiveness factor (eta) of an immobilized enzyme?**
Effectiveness factor = (observed reaction rate) / (reaction rate if there were no diffusion limitation). It ranges from 0 to 1. An eta of 1 means no diffusion limitation. An eta of 0.3 means the enzyme is only operating at 30% efficiency due to mass transfer resistance.

**Q17. How would you determine the effectiveness factor experimentally?**
Compare the activity of immobilized enzyme beads with the activity of the same amount of free enzyme under identical conditions. eta = V_immobilized / V_free.

**Q18. What is the Thiele modulus?**
The Thiele modulus (phi) is a dimensionless number that relates the reaction rate to the diffusion rate:
phi = (R / 3) x sqrt(Vmax / (Km x De))
where R = bead radius, De = effective diffusivity. A large phi means diffusion limitation is significant. A small phi means diffusion is fast relative to reaction.

**Q19. Why is entrapment considered a "physical" method while covalent binding is "chemical"?**
In entrapment, there is no chemical bond between the enzyme and the alginate. The enzyme is just physically trapped in the gel mesh -- like a marble in jelly. The enzyme's structure and active site are unchanged. In covalent binding, a chemical bond forms between functional groups on the enzyme (like -NH2, -SH, -COOH) and the support. This can sometimes alter the active site and reduce activity.

**Q20. How long can alginate beads be stored? What limits their shelf life?**
They can typically be stored for days to weeks at 4 deg C in buffer (25 mM sodium acetate, pH 5.5). Shelf life is limited by: enzyme denaturation over time, microbial contamination of the beads, alginate degradation, and calcium leaching out (which weakens the gel). Adding 0.02% sodium azide prevents microbial growth. EDTA (a calcium chelator) should be avoided as it dissolves the beads.

---
---

# EXPERIMENT 5: DETERMINATION OF Km AND Vmax OF ALPHA-AMYLASE IMMOBILIZED ON GELATIN MATRIX BY CROSS-LINKING

## Aim
1. To immobilize alpha-amylase in gelatin matrix by cross-linking with glutaraldehyde
2. To determine the kinetic constants Km and Vmax of this gelatin-immobilized enzyme

---

## Detailed Explanation in Simple Words

### What's Different from Experiment 4?

In Experiment 4, the enzyme was **entrapped** in alginate beads (trapped inside a gel like a marble in jelly). The enzyme just sits there with no chemical attachment to the alginate.

In this experiment, the enzyme is **cross-linked** within a gelatin matrix using glutaraldehyde. This is a fundamentally different approach:
- The enzyme is chemically bonded into the gelatin network
- Glutaraldehyde acts as a "molecular glue" that creates covalent bonds between the enzyme and the gelatin
- The result is small gelatin chips with enzyme permanently locked inside

### What is Gelatin?

Gelatin is derived from collagen (the protein in animal bones and skin). When you heat collagen in water, it breaks down into gelatin. Gelatin dissolves in warm water and sets into a jelly when cooled -- this is why jelly desserts work.

**Why use gelatin for immobilization?**
- Cheap and abundant (made from animal waste)
- Easy to handle (dissolves in warm water, sets when cool)
- Contains lots of amino groups (-NH2) on its surface, which glutaraldehyde can grab onto
- Biocompatible (won't poison the enzyme)
- Forms a heterogeneous mixture of single and multi-stranded polypeptides, which enhances stability

### What is Glutaraldehyde and How Does Cross-Linking Work?

Glutaraldehyde is a small molecule with the formula OHC-(CH2)3-CHO. It has an aldehyde group (-CHO) on each end. Each aldehyde can react with an amino group (-NH2) to form a Schiff base (C=N bond).

So glutaraldehyde works as a bridge:

```
Gelatin-NH2  +  OHC-CH2-CH2-CH2-CHO  +  H2N-Enzyme
                 (glutaraldehyde)
                        |
                        v
Gelatin-N=CH-CH2-CH2-CH2-CH=N-Enzyme
         (cross-linked product)
```

One end of glutaraldehyde grabs the gelatin, the other end grabs the enzyme. This locks the enzyme in place with covalent bonds. Unlike entrapment, the enzyme cannot leak out.

### How the Gelatin-Enzyme Chips Were Made

**Step 1: Make gelatin solution**
- Dissolved 20 g gelatin in 100 ml distilled water by heating at 50 deg C
- Cooled to room temperature (but kept it liquid)

**Step 2: Add enzyme**
- Dissolved 0.1 g (100 mg) of alpha-amylase in 1 ml of 0.1 M potassium phosphate buffer
- Added this 1 ml of enzyme stock (0.1 g/ml) to the gelatin solution
- Mixed thoroughly to get a final enzyme concentration of ~1 mg/ml

**Step 3: Cast the gel**
- Poured the mixture onto pre-assembled glass plates (like making a flat sheet of jelly)
- Let it cool and set (jellify) for about 30 minutes

**Step 4: Cross-link**
- Added 10 ml of 10% glutaraldehyde solution on top of the set gelatin
- Left at 4 deg C (refrigerator) for 10-15 minutes for complete hardening
- The glutaraldehyde diffuses into the gelatin, creating cross-links between gelatin chains and between gelatin and enzyme molecules

**Step 5: Cut into chips**
- Cut the cross-linked gelatin sheet into small chips (3 x 3 mm) using a sharp scalpel
- Washed the chips with 0.1 M potassium phosphate buffer to remove unbound enzyme and excess glutaraldehyde

**Step 6: Check enzyme loss**
- Measured protein in the first wash using Lowry's method
- This tells you how much enzyme leaked out (was not cross-linked)

**Step 7: Make blank chips**
- Same procedure but without enzyme (gelatin + glutaraldehyde only)
- Used as controls in the DNS assay

**Storage**: Chips stored in 25 mM sodium acetate buffer, pH 5.5, at 4 deg C.

### Measuring Km and Vmax

**Starch concentrations used**: 0.02%, 0.03%, 0.04%, 0.05%, 0.06%, 0.07% (w/v) in 100 mM phosphate buffer

**Procedure for each concentration:**
1. Made 6 ml of starch solution for each concentration
2. Added 1.5 g of amylase-immobilized gelatin chips to each (weighed on balance)
3. Also made blanks with 1.5 g of blank gelatin chips (no enzyme)
4. Incubated at 37 deg C on a shaking incubator
5. Collected supernatant samples at 0, 3, and 5 minutes
6. Performed DNS assay on each sample
7. Calculated maltose concentration at each time point

### Enzyme Loss Calculation

From BSA standard curve (Experiment 2): y = 1.0023x

- Wash water OD at 660 nm = 0.363
- Protein concentration = 0.363 / 1.0023 = 0.365 mg/ml
- Total wash volume = 50 ml
- **Total enzyme lost = 0.365 x 50 = 18.25 mg** (out of 100 mg loaded)

So about 18% of the enzyme was not cross-linked and washed away. The remaining ~82 mg is permanently attached within the gelatin chips.

### Results

**Initial rates:**
- For 0.02% starch: V0 = 0.0343 mM/min
- For 0.03% starch: V0 = 0.014 mM/min

**Lineweaver-Burk plot equation:** y = 83.421x + 8.8521 (R-squared = 0.9943)

| Parameter | Value |
|-----------|-------|
| 1/Vmax (y-intercept) | 8.8521 |
| **Vmax** | **0.113 umol/ml/min** |
| Slope (Km/Vmax) | 83.421 |
| **Km** | **83.421 x 0.113 = 9.42 mM** |

### Comparison Table (All Three Forms)

| Parameter | Free Enzyme (Exp 3) | Alginate Beads (Exp 4) | Gelatin Cross-linked (Exp 5) |
|-----------|--------------------|-----------------------------|-------------------------------|
| Vmax | 0.5387 mM/min | 0.093 mM/min | 0.113 umol/ml/min |
| Km | 7.41 x 10^-5 mM | 1.672 x 10^-5 | 9.42 mM |

The gelatin-immobilized enzyme shows higher Km compared to both free and alginate-immobilized forms, suggesting that the cross-linking with glutaraldehyde or the gelatin matrix may cause some structural change in the enzyme, reducing its affinity for starch.

---

## Viva Questions -- Experiment 5

### Basic Level

**Q1. What is cross-linking in enzyme immobilization?**
Cross-linking uses a bifunctional reagent (a molecule with two reactive ends, like glutaraldehyde) to create covalent bonds between enzyme molecules and/or between enzyme and support material. This permanently attaches the enzyme.

**Q2. What is glutaraldehyde?**
Glutaraldehyde (OHC-CH2-CH2-CH2-CHO) is a 5-carbon dialdehyde commonly used as a cross-linking agent in biochemistry. Each aldehyde end reacts with free amino groups (-NH2) on proteins to form Schiff base linkages (C=N bonds).

**Q3. What is gelatin?**
Gelatin is a protein derived from partial hydrolysis of collagen (found in animal skin, bones, and connective tissue). It dissolves in warm water and forms a gel when cooled.

**Q4. Why is gelatin a good matrix for enzyme immobilization?**
It is cheap, abundant, biocompatible, easy to work with (dissolves at 50 deg C, gels at room temperature), and has many free amino groups that react with glutaraldehyde for cross-linking.

**Q5. Why were the chips washed after cross-linking?**
To remove unreacted glutaraldehyde (which is toxic and could denature the enzyme over time) and to remove enzyme molecules that were not cross-linked (they would leak out during use and give false results).

---

### Intermediate Level

**Q6. How is cross-linking different from entrapment?**
- **Entrapment**: Enzyme is physically trapped inside a gel (no chemical bond). It can potentially leak out through pores.
- **Cross-linking**: Enzyme is covalently bonded. It cannot leak out. But the chemical modification can alter the enzyme's structure and reduce activity.

**Q7. What is a Schiff base?**
A Schiff base is a compound with a carbon-nitrogen double bond (C=N). It forms when an aldehyde (-CHO) reacts with a primary amine (-NH2): R-CHO + H2N-R' --> R-CH=N-R' + H2O. In this experiment, glutaraldehyde forms Schiff bases with amino groups on both gelatin and the enzyme.

**Q8. Why was the Km of gelatin-immobilized enzyme much higher than free enzyme?**
Several possible reasons:
1. Glutaraldehyde may have cross-linked near the active site, partially blocking substrate access
2. The gelatin matrix creates steric hindrance (starch is a large molecule and has trouble reaching the enzyme)
3. Cross-linking may cause conformational changes that reduce substrate affinity
4. Diffusion of the large starch molecules through the dense gelatin gel is restricted

**Q9. Why was enzyme activity still present despite cross-linking?**
Glutaraldehyde primarily reacts with lysine residues (-NH2 groups) on the protein surface. If the active site of amylase doesn't have critical lysine residues, the catalytic function is preserved even though the enzyme's outer surface is modified.

**Q10. Why store the chips at 4 deg C in sodium acetate buffer?**
Low temperature (4 deg C) slows down enzyme denaturation and prevents microbial growth. Sodium acetate buffer at pH 5.5 provides a mildly acidic environment that helps maintain gelatin stability (gelatin softens at neutral pH and warm temperatures).

**Q11. How do you calculate how much enzyme is in each gram of gelatin chip?**
Total enzyme loaded minus enzyme lost in wash = enzyme retained. Divide by total weight of chips produced. In this case: (100 - 18.25) mg / total chip weight = mg enzyme per gram of chip.

---

### Advanced Level

**Q12. What happens if you use too much glutaraldehyde?**
Excess glutaraldehyde causes over-cross-linking. The enzyme becomes too rigid -- it can't flex during catalysis (enzymes need some conformational flexibility to work). The active site may become distorted. Activity drops sharply. You need to optimise the glutaraldehyde concentration.

**Q13. What happens if you use too little glutaraldehyde?**
Insufficient cross-linking means the gelatin matrix is soft and unstable. Enzyme can leak out. The chips may dissolve or disintegrate during use.

**Q14. Compare the advantages and disadvantages of alginate entrapment vs gelatin cross-linking.**

| Feature | Alginate Entrapment | Gelatin Cross-linking |
|---------|--------------------|-----------------------|
| Enzyme retention | Some leakage possible | Very good (covalent bonds) |
| Activity retention | Better (no chemical modification) | May be lower (cross-linking can affect active site) |
| Mechanical strength | Moderate (beads can be fragile) | Good (cross-linked protein matrix) |
| Diffusion | Moderate limitation | Higher limitation (denser matrix) |
| Ease of preparation | Easy (just drip into CaCl2) | More steps (casting, cross-linking, cutting) |
| Cost | Low | Slightly higher (glutaraldehyde cost) |
| Reusability | Limited (beads soften over time) | Good (covalent bonds are stable) |

**Q15. What is the Michael-type addition reaction that glutaraldehyde undergoes?**
Glutaraldehyde in aqueous solution exists as alpha,beta-unsaturated oligomers. The reaction with amino groups can occur via:
1. Schiff base formation (aldehyde + amine)
2. Michael-type 1,4-addition (amine adds to the C=C of an alpha,beta-unsaturated carbonyl)
Both mechanisms contribute to cross-linking, and the Michael addition products are often more stable than simple Schiff bases.

**Q16. How would you optimize the glutaraldehyde concentration?**
Test a range (0.5%, 1%, 2.5%, 5%, 10%, 15% glutaraldehyde). For each, measure:
- Enzyme activity retention (should be maximized)
- Mechanical stability of chips (should be sufficient)
- Enzyme leakage in wash (should be minimized)
Plot all three against glutaraldehyde concentration. The optimal concentration is where you get good mechanical stability and low leakage without too much activity loss.

---
---

# EXPERIMENT 6: PERFORMANCE OF IMMOBILIZED AMYLASE ENZYME IN CSTR OPERATED WITH DIFFERENT FLOW RATES FOR STARCH HYDROLYSIS

## Aim
To study the kinetics of immobilized amylase enzyme in a Continuous Stirred Tank Reactor (CSTR) operated with different flow rates for starch hydrolysis.

---

## Detailed Explanation in Simple Words

### What is a CSTR?

A CSTR (Continuous Stirred Tank Reactor) is a well-mixed reactor where:
- Fresh substrate solution continuously flows IN
- Product-containing solution continuously flows OUT
- A stirrer keeps everything perfectly mixed inside
- Immobilized enzyme beads stay inside the reactor (they're too big to leave through the outlet)

Think of it like a bathtub with the tap on and the drain open at the same time. Water continuously comes in and goes out. If you add soap (enzyme beads) to the tub, the soap stays in the tub but the water flowing out carries whatever the soap helped dissolve.

### How a CSTR Is Different from a Batch Reactor

| Feature | Batch Reactor | CSTR |
|---------|--------------|------|
| Substrate addition | All at once, at the start | Continuously flows in |
| Product removal | All at the end | Continuously flows out |
| Operation | Start -> run -> stop -> harvest | Runs continuously for long periods |
| Enzyme use | Once per batch (unless immobilized) | Immobilized enzyme stays inside, reused continuously |
| Concentration inside | Changes with time | Reaches a steady state (constant) |

### Key Concepts

**Flow rate (F):** How fast the liquid flows through the reactor, in ml/min. A higher flow rate means liquid spends less time in the reactor.

**Reactor volume (V):** The liquid volume inside the reactor. In this experiment, V = 400 ml.

**Dilution rate (D):** D = F/V (in min^-1 or per minute). It tells you how many times per minute the reactor volume is "replaced" by fresh feed.
- If F = 10 ml/min and V = 400 ml, then D = 10/400 = 0.025 min^-1

**Residence time (tau):** tau = V/F = 1/D. It's the average time a molecule of substrate spends inside the reactor.
- If D = 0.025 min^-1, then tau = 1/0.025 = 40 minutes

**Steady state:** After some time, the concentration of product coming out becomes constant -- it doesn't change from minute to minute. This is the steady state. It means the rate of substrate coming in equals the rate of substrate being consumed + the rate of unreacted substrate going out.

### Why Does Flow Rate Matter?

- **Slow flow rate** (long residence time): Substrate spends a lot of time in the reactor. The enzyme has plenty of time to convert it. More product, higher conversion.
- **Fast flow rate** (short residence time): Substrate rushes through. The enzyme doesn't have enough time to convert much of it. Less product, lower conversion.

There's a trade-off: slow flow = more conversion but less throughput. Fast flow = less conversion but more throughput. You need to find the sweet spot.

### What Was Done in the Experiment

**Setup:**
- CSTR vessel with V = 400 ml
- 100 alginate beads containing immobilized amylase added to the reactor
- Feed tank filled with 0.01% (w/v) starch solution
- Peristaltic pump controlled the flow rate
- Temperature maintained at constant level
- Stirrer keeps the beads and solution well mixed

**Procedure:**
1. Ran the CSTR at 4 different flow rates: 10, 20, 30, and 40 ml/min
2. For each flow rate, operated for 20 minutes
3. Collected 5 ml samples every 5 minutes (at 0, 5, 10, 15, 20 min)
4. Did DNS assay on each sample to measure maltose concentration
5. Looked for when the maltose concentration stabilized (steady state)

### Results

| Flow Rate (ml/min) | D = F/V | Residence Time (min) | Steady-State Maltose Conc. (mM) |
|--------------------|---------|---------------------|----------------------------------|
| 10 | 0.025 | 40 | 0.058 |
| 20 | 0.05 | 20 | 0.01548 |
| 30 | 0.075 | 13.33 | No clear steady state reached |
| 40 | 0.1 | 10 | 0.0232 |

### What the Results Mean

1. **At 10 ml/min (slowest flow):** The substrate stayed for 40 minutes. Plenty of time for the enzyme to work. Highest maltose concentration (0.058 mM). Best conversion.

2. **At 20 ml/min:** Residence time drops to 20 minutes. Less conversion. Maltose = 0.01548 mM.

3. **At 30 ml/min:** The product concentration kept changing over the 20-minute run -- it never settled to a constant value. No true steady state was reached. This is because at this flow rate, the system needed more time to stabilize.

4. **At 40 ml/min (fastest flow):** Short residence time (10 min). Substrate rushes through. Maltose = 0.0232 mM.

**The graph of steady-state maltose vs dilution rate showed a non-linear (hyperbolic-like) decrease:** As you increase the flow rate, the product concentration drops -- because the substrate has less time to react. The highest conversion was at the lowest flow rate.

### The Key Takeaway

In a CSTR, lowering the flow rate increases the conversion (more product) because the substrate stays inside longer. But going too slow reduces your throughput (total amount of product per day). Industrial operation aims for the best balance.

---

## Viva Questions -- Experiment 6

### Basic Level

**Q1. What is a CSTR?**
A Continuous Stirred Tank Reactor is a well-mixed reactor where substrate flows in continuously, product flows out continuously, and immobilized enzyme stays inside. A stirrer ensures the contents are uniformly mixed.

**Q2. What is dilution rate?**
Dilution rate (D) = Flow rate (F) / Reactor volume (V). Units: per minute (min^-1) or per hour (h^-1). It tells you how quickly the reactor contents are being replaced.

**Q3. What is residence time?**
Residence time (tau) = V/F = 1/D. It is the average time a molecule of substrate spends inside the reactor before exiting.

**Q4. What is steady state?**
Steady state is the condition where the concentration of substrate and product inside the reactor (and in the exit stream) does not change with time. The rate of substrate consumption by the enzyme equals the rate at which fresh substrate is supplied.

**Q5. Why did higher flow rates give lower product concentration?**
Because at higher flow rates, the substrate spends less time in the reactor (shorter residence time). The enzyme has less time to convert starch to maltose. So less product is formed.

**Q6. Why were immobilized enzyme beads used instead of free enzyme?**
Free enzyme would flow out of the reactor with the exit stream. Immobilized beads are large enough to stay inside the reactor while liquid flows past them, allowing continuous reuse of the enzyme.

---

### Intermediate Level

**Q7. Why was no steady state achieved at 30 ml/min?**
The 20-minute operating period was too short for this flow rate. The system needed more time for the product concentration to stabilize. The residence time was 13.33 minutes, and transients (start-up fluctuations) hadn't dampened out by the end of the experiment.

**Q8. What is the relationship between dilution rate and steady-state product concentration?**
It's inverse and non-linear. As D increases, tau decreases, and steady-state product concentration decreases (less time for conversion). At very high D, the product concentration approaches zero. At very low D, it approaches the maximum possible conversion.

**Q9. In a CSTR, the exit stream has the same composition as the reactor contents. Why?**
Because the reactor is perfectly mixed. The stirrer ensures that every point inside the reactor has the same concentration. So whatever concentration exists inside is what flows out.

**Q10. What is washout?**
If the flow rate is too high (dilution rate exceeds a critical value), the substrate rushes through so fast that hardly any conversion occurs. In cell culture CSTRs, cells can actually wash out (be carried out faster than they can grow). With immobilized enzymes, the enzyme stays but the conversion drops to near zero.

**Q11. How would you calculate the conversion in the CSTR?**
Conversion = (Substrate_in - Substrate_out) / Substrate_in = (S0 - S) / S0. You can also estimate it from the product formed: if all converted substrate becomes product, then product concentration / initial substrate concentration gives a measure of conversion.

**Q12. Why is temperature control important in a CSTR?**
Enzyme activity depends on temperature. If temperature fluctuates, so does the conversion rate, making it hard to reach a true steady state. A constant temperature ensures reproducible kinetics.

---

### Advanced Level

**Q13. Write the mass balance equation for substrate in a CSTR with immobilized enzyme.**
At steady state, rate in = rate out + rate consumed:
F x S0 = F x S + V x r_s
Where S0 = inlet substrate concentration, S = outlet (and reactor) concentration, r_s = rate of substrate consumption.

Rearranging: r_s = D(S0 - S)

If the enzyme follows Michaelis-Menten kinetics: r_s = Vmax x S / (Km + S)

So: D(S0 - S) = Vmax x S / (Km + S)

This equation lets you predict steady-state S for any D, or find what D gives you a desired S.

**Q14. How would you design a CSTR for maximum productivity?**
Productivity = D x P (dilution rate x product concentration). There's an optimum D that maximizes this. Too low D gives high P but low throughput. Too high D gives high throughput but almost no P. Take the derivative of D x P with respect to D and set it to zero.

**Q15. What are the advantages of CSTR over PBR (Packed Bed Reactor)?**
- Better mixing (uniform concentration throughout)
- Better temperature control
- Easier to handle viscous or particulate substrates
- Easier to add/remove beads or adjust conditions

**Disadvantages vs PBR:**
- Lower conversion per pass (because substrate mixes with product, diluting the driving force)
- Requires mechanical stirring (energy cost)
- More back-mixing means substrate always "sees" the lower steady-state concentration, not the full inlet concentration

**Q16. How does a CSTR compare to a PBR in terms of conversion for the same enzyme and flow rate?**
For the same enzyme amount and flow rate, a PBR generally gives higher conversion than a CSTR. This is because in a PBR, substrate concentration decreases along the column (like a series of small batch reactions), so the average driving force is higher. In a CSTR, the enzyme always works at the low, exit concentration.

**Q17. If you could run this experiment for 2 hours instead of 20 minutes, what would change?**
All flow rates would likely reach steady state (even the 30 ml/min case). You would get more reliable steady-state data. The actual steady-state concentrations would be the same -- they're determined by the kinetics and flow rate, not by how long you run.

---
---

# EXPERIMENT 7: PERFORMANCE OF AN IMMOBILIZED ENZYME PACKED BED REACTOR (PBR) OPERATED AT DIFFERENT FLOW RATES FOR STARCH HYDROLYSIS

## Aim
To study the performance of an immobilized enzyme Packed Bed Reactor (PBR) operated at different flow rates for starch hydrolysis.

---

## Detailed Explanation in Simple Words

### What is a Packed Bed Reactor (PBR)?

A PBR is a vertical tube (column) that is filled ("packed") with immobilized enzyme beads. Substrate solution is pumped in from one end, flows through the bed of beads, and exits from the other end with the product.

Think of it like a water filter. The filter cartridge is packed with granules. Water goes in dirty and comes out clean. In a PBR, starch solution goes in from the bottom and comes out from the top as maltose (sugar) solution.

### How PBR Is Different from CSTR

| Feature | CSTR | PBR |
|---------|------|-----|
| Mixing | Perfectly mixed (same concentration everywhere) | No mixing (concentration changes along the column -- called plug flow) |
| Substrate concentration | Same everywhere inside (equal to exit concentration) | Highest at the inlet, lowest at the outlet (decreases along the length) |
| Enzyme contact | Enzyme beads are suspended and mixed | Enzyme beads are packed and stationary |
| Conversion per pass | Lower (enzyme works at the low exit concentration) | Higher (enzyme near inlet works at high concentration, enzyme near outlet works at low concentration -- better average) |
| Back-mixing | Complete back-mixing | No back-mixing (ideally) |
| Particle damage | More (stirrer can grind beads) | Less (beads sit still) |

### PBR Setup

The PBR in this experiment consisted of:
- **A vertical glass column** packed with 60 g of alginate beads (containing immobilized amylase)
- **Outer water jacket** for temperature control (maintains isothermal conditions)
- **Distributor (perforated disc)** at the bottom with 0.5 mm pore size -- spreads the incoming liquid evenly across the column cross-section
- **Piston at top** for volume adjustment
- **Peristaltic pump** drawing substrate from the feed tank and pushing it into the column
- **Feed tank** with 0.1% (w/v) starch solution
- **Collection tank** at the exit for collecting the product
- Gelatin-like beads of 1-3 mm size packed in the column

### How Substrate Flows Through the PBR

The substrate enters at the bottom and flows upward through the gaps between the beads. As it travels up:

1. Near the **bottom (inlet)**: Starch concentration is highest. Enzyme here works fast because there's plenty of substrate.
2. In the **middle**: Some starch has already been converted. Concentration is moderate. Enzyme works at a moderate speed.
3. Near the **top (outlet)**: Most of the starch has been converted. Very little starch left. Enzyme here works slowly.

The product (maltose) concentration does the opposite -- zero at the inlet, maximum at the outlet.

### Key PBR Concepts

**Packed volume (V_packed):** The volume occupied by the beads in the column. Calculated from column height and inner diameter.

**Void volume:** The liquid volume in the gaps between beads. Typically 30-40% of the packed volume.

**Space time:** V_packed / F (similar to residence time in CSTR, but based on the packed volume).

### What Was Done

**Step 1:** Prepared 10 L of 0.1% starch solution (substrate feed)

**Step 2:** Calibrated the peristaltic pump to deliver known flow rates

**Step 3:** Filled the feed tank with starch solution

**Step 4:** Packed the PBR column with 60 g of alginate beads

**Step 5:** Measured the packed volume from column height and inner diameter

**Step 6:** Maintained isothermal conditions using the water jacket

**Step 7:** Ran the PBR at three different flow rates: 10 ml/min, 20 ml/min, and 30 ml/min

**Step 8:** For each flow rate, operated for 40+ minutes or until steady state was reached

**Step 9:** Collected 5 ml samples at 5-minute intervals from the exit

**Step 10:** Performed DNS assay on each sample to measure maltose in the exit stream

**Step 11:** Looked for steady state (when maltose concentration in the exit stopped changing)

### What Makes a Good PBR?

1. **Beads should be incompressible** -- they shouldn't get squished under the weight of beads above them. If they deform, they block liquid flow.
2. **Beads should be uniform in size** -- for even flow distribution. If some are big and some small, liquid takes the path of least resistance (channels through the big gaps) and bypasses some enzyme.
3. **No channelling** -- liquid should flow evenly through the entire cross-section, not just through a few preferred paths.
4. **Clean, debris-free medium** -- particles in the feed can clog the spaces between beads and block flow.

### Commercial Uses of PBRs

Packed bed reactors with immobilized enzymes/cells have been used commercially for:
- Production of **aspartate** (amino acid)
- Production of **fumarate** (organic acid)
- Production of **penicillin** (antibiotic)
- Resolution of **amino acid isomers** (separating L and D forms)
- High fructose corn syrup production (glucose isomerase on PBR)

### Calculations

**Enzyme activity formula:**
```
Enzyme Activity = OD(test) x concentration of starch (umoles) x dilution of enzyme
                  ------------------------------------------------------------------
                  OD(starch) x incubation time
```

**Enzyme unit** = micromoles maltose formed per minute per 0.5 ml enzyme (x2) = micromoles maltose formed per minute per ml enzyme

### Key Results and Observations

At lower flow rates:
- Substrate stays in the column longer
- More starch gets converted to maltose
- Higher product concentration in the exit stream

At higher flow rates:
- Substrate passes through quickly
- Less conversion
- Lower product concentration

This confirms that residence time is the critical factor -- longer contact time between substrate and enzyme means more product.

---

## Viva Questions -- Experiment 7

### Basic Level

**Q1. What is a Packed Bed Reactor (PBR)?**
A PBR is a tubular reactor packed with immobilized enzyme particles (beads). Substrate flows through the bed, contacts the enzyme, and exits as product. There is no mechanical stirring.

**Q2. How does substrate flow in a PBR?**
Substrate enters at one end (usually bottom), flows through the gaps between the packed enzyme beads, and exits at the other end (top). The flow is approximately "plug flow" -- all molecules spend roughly the same time in the reactor.

**Q3. Why use a PBR instead of a CSTR?**
PBR gives higher conversion per pass because there's no back-mixing. The substrate concentration decreases gradually along the column, so the enzyme always works at the local concentration rather than the diluted exit concentration.

**Q4. What is the role of the distributor disc at the bottom?**
It has small holes (0.5 mm pores) that spread the incoming liquid evenly across the entire cross-section of the column. Without it, liquid might flow through just one side ("channelling"), leaving some enzyme unused.

**Q5. Why is a water jacket provided around the column?**
To maintain constant temperature (isothermal conditions). The enzymatic reaction rate depends on temperature, so fluctuations would give unreliable results.

**Q6. Why is there a piston at the top of the column?**
To adjust the packed volume. You can push the piston down to compress the bed slightly (removing air gaps) or pull it up to reduce back-pressure.

---

### Intermediate Level

**Q7. What is the difference between plug flow (PBR) and mixed flow (CSTR)?**
- **Plug flow (PBR):** All molecules travel through the reactor in order -- like cars in a tunnel. No back-mixing. Concentration changes along the length. Those entering first exit first.
- **Mixed flow (CSTR):** Everything is stirred together. A molecule that just entered might exit immediately, or it might stay for a long time. Complete back-mixing. Uniform concentration throughout.

**Q8. Why does a PBR give higher conversion than a CSTR for the same enzyme amount and flow rate?**
In a PBR, the enzyme near the inlet works at high substrate concentration (fast rate), while enzyme near the exit works at low concentration (slow rate). The average rate is higher. In a CSTR, ALL the enzyme works at the low exit concentration (because everything is mixed). So the average rate is lower.

**Q9. What is channelling and why is it bad?**
Channelling occurs when liquid flows preferentially through certain paths (channels) in the packed bed while bypassing other regions. This means some enzyme beads don't contact the substrate, reducing effective conversion. Caused by uneven packing, broken beads, or non-uniform bead sizes.

**Q10. What properties should the beads have for PBR use?**
- **Incompressible** -- must not deform under the weight of beads above
- **Uniform size** -- for even flow distribution
- **Chemically stable** -- should not dissolve or degrade in the substrate solution
- **Adequate porosity** -- substrate must be able to diffuse into the bead
- **Mechanically strong** -- should not break or crumble

**Q11. What is space time in a PBR?**
Space time = packed bed volume / volumetric flow rate = V_packed / F. It represents the average time the liquid spends in contact with the packed bed. Similar to residence time but specifically refers to the packed region.

**Q12. Why was 0.1% starch used and not a higher concentration?**
Higher starch concentrations would increase viscosity, making it harder to pump through the packed bed. Also, too much starch could produce absorbance values beyond the linear range of the DNS assay.

---

### Advanced Level

**Q13. Write the mass balance for a differential element of a PBR.**
For a thin slice of the column (thickness dz):
F x dS = -r_s x A x dz

Where F = flow rate, S = substrate concentration, r_s = reaction rate per unit volume of bed, A = cross-sectional area.

Integrating from inlet to outlet:
Integral from S0 to S of dS/r_s = -(A/F) x integral from 0 to L of dz = -V_packed/F

If Michaelis-Menten kinetics apply:
V_packed/F = integral from S to S0 of (Km + S)/(Vmax x S) dS

**Q14. What is the Damkohler number and what does it tell you?**
The Damkohler number (Da) = Vmax x tau / (Km + S0), where tau is the space time. It compares the reaction rate to the flow rate.
- Da >> 1: Reaction is fast compared to flow. High conversion.
- Da << 1: Reaction is slow compared to flow. Low conversion.
- Da ~ 1: Both are comparable. Intermediate conversion.

**Q15. How would you scale up a PBR?**
- Maintain the same space time (V_packed/F ratio)
- Keep the same linear velocity (flow rate per unit cross-sectional area) to maintain similar mass transfer conditions
- Increase column diameter rather than length (to avoid excessive pressure drop)
- Use the same bead size and packing method

**Q16. What is pressure drop in a PBR and why does it matter?**
As liquid flows through the packed bed, it encounters resistance from the beads. This creates a pressure difference between inlet and outlet (pressure drop). Described by the Ergun equation. High pressure drop can:
- Compress soft beads
- Require more powerful pumps
- Cause channelling if beads deform
Smaller beads, longer columns, higher flow rates, and more viscous liquids all increase pressure drop.

**Q17. Compare PBR and CSTR: when would you choose one over the other?**

| Choose PBR when... | Choose CSTR when... |
|--------------------|--------------------|
| High conversion per pass is needed | Substrate is viscous or contains particles |
| Substrate is a clear liquid | Good temperature control is critical |
| Enzyme beads are mechanically strong | Need to add/remove catalyst easily |
| Low flow rates are acceptable | Substrate inhibition is a problem (CSTR keeps S low) |
| No need to add/remove beads during operation | Need flexibility to change conditions quickly |

**Q18. What would happen if you ran the PBR in downflow mode instead of upflow?**
Downflow can cause compaction of the bed (gravity + flow pressure push beads together), increasing pressure drop and reducing void volume. Upflow mode "fluidizes" the bed slightly, keeping it loose. However, upflow can cause bed expansion if the flow rate is too high (fluidized bed behaviour).

**Q19. In this experiment, gelatin beads were used. How do they compare to alginate beads for PBR?**
Gelatin cross-linked beads (1-3 mm) tend to be mechanically stronger than alginate beads, making them better suited for PBR where beads must withstand the weight of the bed above and the pressure of liquid flow. Alginate beads can soften over time, especially if calcium leaches out. However, gelatin beads have denser structure which increases internal diffusion resistance.

**Q20. What is the concept of "washout" in a PBR context?**
Washout is less relevant for PBR with immobilized enzyme (beads stay in place). But at very high flow rates, the residence time becomes so short that almost no conversion occurs -- the substrate passes through essentially unreacted. The practical effect is the same: product concentration drops to near zero.

---
---

# SUMMARY COMPARISON TABLE -- ALL EXPERIMENTS

| Exp | What Was Done | Key Technique | Key Result |
|-----|--------------|---------------|------------|
| 1 | Studied fermenter design | Study/diagram | Learned all 17+ components and their functions |
| 2 | Measured amylase activity | DNS assay + Lowry | Activity = 0.214 umol/min/ml, Specific = 0.80 umol/min/mg |
| 3 | Found Km, Vmax of free amylase | Lineweaver-Burk plot | Vmax = 0.539 mM/min, Km = 7.41 x 10^-5 mM |
| 4 | Found Km, Vmax of alginate-immobilized amylase | Ca-alginate entrapment + LB plot | Vmax = 0.093 mM/min, Km = 1.67 x 10^-5 umol/ml |
| 5 | Found Km, Vmax of gelatin-immobilized amylase | Gelatin cross-linking + LB plot | Vmax = 0.113 umol/ml/min, Km = 9.42 mM |
| 6 | CSTR performance at different flow rates | Continuous stirred tank reactor | Lower flow rate = higher conversion. Steady state not reached at 30 ml/min |
| 7 | PBR performance at different flow rates | Packed bed reactor | Lower flow rate = higher conversion. PBR gives better conversion than CSTR |

---

# BONUS: GENERAL VIVA QUESTIONS (Across All Experiments)

These questions can come from any experiment. They test your overall understanding.

**Q1. What is the difference between a batch reactor, CSTR, and PBR?**
- Batch: All in, react, all out. No flow during reaction.
- CSTR: Continuous flow, perfectly mixed, enzyme works at exit concentration.
- PBR: Continuous flow, no mixing, enzyme works at local concentration along the column.

**Q2. Why is the DNS method preferred for measuring reducing sugars in enzyme assays?**
It is simple, cheap, fast, and works for all reducing sugars. The colour is stable (with Rochelle salt) and the method is well-standardized.

**Q3. What is the Beer-Lambert law?**
A = epsilon x c x l, where A = absorbance, epsilon = molar extinction coefficient, c = concentration (mol/L), l = path length (cm). Absorbance is proportional to concentration -- this is why spectrophotometric assays work.

**Q4. Why is phosphate buffer used at pH 7 in most of these experiments?**
Amylase works best at neutral pH. Phosphate buffer has good buffering capacity around pH 7 and doesn't interfere with the DNS or Lowry assays.

**Q5. Name 3 industrial applications of immobilized enzymes.**
1. High-fructose corn syrup (HFCS) production using immobilized glucose isomerase
2. Production of 6-aminopenicillanic acid (6-APA) from penicillin using immobilized penicillin acylase
3. Production of L-amino acids from racemic mixtures using immobilized aminoacylase

**Q6. What is the difference between enzyme activity and specific activity?**
- Enzyme activity = total catalytic power (umol product/min/ml)
- Specific activity = catalytic power per mg of protein (umol product/min/mg). Indicates enzyme purity.

**Q7. Why does immobilization generally decrease Vmax?**
Diffusion limitations. Substrate must travel through a gel/matrix to reach the enzyme. Product must travel back out. This mass transfer resistance means the enzyme never truly "sees" the full external substrate concentration, so the effective maximum rate drops.

**Q8. What is the significance of R-squared (R^2) in graph analysis?**
R-squared tells you how well your data fits the trend line. R^2 = 1 means perfect fit. R^2 = 0.99+ is excellent. R^2 < 0.90 suggests your model may not be appropriate or there's significant experimental error.

**Q9. Why do you need both a maltose standard curve and a BSA standard curve?**
- Maltose standard curve: Converts DNS assay absorbance to maltose concentration (measures enzyme activity)
- BSA standard curve: Converts Lowry assay absorbance to protein concentration (measures enzyme amount)
You need both to calculate specific activity.

**Q10. If you were starting a biotech company that uses amylase for starch processing, would you use free or immobilized enzyme? Which reactor type?**
Immobilized enzyme in a PBR is the industry standard for starch processing. Reasons: enzyme is reusable (lower cost), continuous operation possible (higher productivity), easy product separation, and PBR gives better conversion per pass than CSTR. This is exactly how HFCS is produced commercially.

---

*This guide covers all 7 experiments from the BPT Lab Record 2025. Each experiment has been explained in plain language with detailed viva questions ranging from basic recall to advanced application-level thinking.*
