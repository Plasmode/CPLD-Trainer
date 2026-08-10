VGA beam racing is a W65C02 overclocked to 25.175MHz, the 60Hz 640×480 VGA dot clock, such that 6502 fetch a byte every 8 clocks that's shifted out to VGA monitor at pixel clock rate. This results in monochrome 640×480 resolution images.
W65C02 is overclocked to 25.175MHz, the 60Hz 640×480 VGA dot clock, such that 6502 fetch a byte every 8 clocks that's shifted out to VGA monitor at pixel clock rate. This results in monochrome 640×480 resolution images. The original concept was discussed here. Additional discussion specific to CPLD trainer was discussed here.
<img width="2830" height="1791" alt="BeamRacing_for_CPLD_Trainer" src="https://github.com/user-attachments/assets/3b10768d-796b-457f-b235-65016800852a" />

<img width="1534" height="1657" alt="CPLD_trainer_25 175mhz_vga_mod" src="https://github.com/user-attachments/assets/6be77b1c-31df-4d47-886a-9e9e9f637c74" />
Engineering change
HD-15 connector is required for VGA connection. Four test points are repurposed for VGA signals. The reason that two test points are used to drive the three VGA data input is because a CPLD output does not have sufficient drive to drive all three VGA inputs, so the loads are splitted between two CPLD outputs.

Test point T28 is VGA Hsync, connect T28 to HD15-pin 13
Test point T29 is VGA Vsync, connect T29 to HD15-pin 14
Test point T7 drives half of VGA input. Connect T7 to HD15-pin 1 via a 330 ohm resistor; connect T7 to HD15-2 via a 680 ohm resistor
Test point T8 drives other half of VGA input. Connect T8 to HD15-pin 3 via a 330 ohm resistor; connect T8 to HD15-2 via a 680 ohm resistor

CPLD design files for beam racing, 
