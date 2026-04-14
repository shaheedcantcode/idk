<img width="1285" height="678" alt="UnlockingUltimatePowerMode" src="https://github.com/user-attachments/assets/1af802fc-c616-48b6-8988-fa1950ff9371" />

The command powercfg -duplicatescheme e9a42b02-d5df-448d-aa00-03f14749eb61 creates a duplicate of the hidden "Ultimate Performance" power plan in Windows.  This plan is designed to maximize performance by disabling power-saving features, often used on high-end desktops or workstations

**What the Command Does**
- powercfg: A built-in Windows utility to manage power plans.
- duplicatescheme: Generates a new copy of an existing power plan using its GUID.
- setactive: This switches your system to the duplicated Ultimate Performance plan.
- GUID e9a42b02-d5df-448d-aa00-03f14749eb61: This specific identifier corresponds to the Ultimate Performance plan introduced in Windows 10 Pro for Workstations and available in Windows 11.

Running this command adds the Ultimate Performance plan to your list of available power plans, even if it’s hidden by default.

**Ultimate Performance Plan Features**
- Disables CPU throttling → Keeps processors running at maximum frequency.
- Minimizes latency → Reduces delays in hardware communication.
- No power-saving compromises → Unlike Balanced or High Performance, it prioritizes raw speed over energy efficiency.

**Best suited for:**
- High-performance desktops
- Workstations running heavy workloads (video editing, 3D rendering, simulations)
- Systems plugged into constant power (Ideally not for laptops, since battery life will suffer)

**Important Notes**
- Administrator rights required: You must run Command Prompt or PowerShell as Administrator, otherwise you’ll get “Access Denied.”
- Battery impact: On laptops, this plan drains battery quickly and may shorten hardware lifespan due to constant high power usage.
- Visibility: After running the command, check available plans via:
  - Control Panel → Hardware and Sound → Power Options
  - Or run powercfg /list in CMD to see all active schemes


  **How to add it**
  - Open up CMD as Administrator
  1. Add the Ultimate Performance Plan
     `powercfg -duplicatescheme e9a42b02-d5df-448d-aa00-03f14749eb61`
     - This duplicates the hidden Ultimate Performance plan
     - Windows will generate a new GUID, which is 8cac6dbb-8153-4bf1-90f6-86a5f0d6ac5c in my case
  2. Activate the New Plan
     `powercfg /setactive 8cac6dbb-8153-4bf1-90f6-86a5f0d6ac5c`
     - This switches your system to the duplicated Ultimate Performance plan, which in my case is this specific GUID
     - Do not use the original GUID, as this tries to activate the original hidden GUID, but it usually won’t work because Windows doesn’t expose it until you duplicate it
     - That’s why you must use the new GUID created in Sequence 1
  3. Check for changes
     - To see all available plans, use: `powercfg /list`
    
  <img width="1110" height="581" alt="UnlockingUltimatePowerModeCMD" src="https://github.com/user-attachments/assets/5cd9e3fe-43b1-4c10-9860-59a93d2b8ce3" />
