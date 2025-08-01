# ATMEGA328 Board
This repository involves designing, assembling, and testing an educational header board for the ATMEGA328 AVR microcontroller, compatible with the Arduino UNO.

![ATMEGA328 Shield](Images/ATEMGA328.png)

> [!IMPORTANT]
> Before sending the board files for PCB fabrication, **always make sure you are using the latest released version** of the project.
> Hardware issues or design flaws might exist in earlier versions and could be fixed in newer releases.
> To avoid costly mistakes and ensure the best performance, always refer to the **[Releases](../../releases)** section, where all known issues, updates, and version-specific notes are clearly documented.

## ATmega328 Pin Mapping Table
| **Arduino Pin** | **ATmega328 Pin**      | **Functionality**                      |
| :-------------: | :--------------------: | :------------------------------------- |
| Analog Pin A0   | PC0 (PORTC, PIN0)      | ADC0                                   |
| Analog Pin A1   | PC1 (PORTC, PIN1)      | ADC1                                   |
| Analog Pin A2   | PC2 (PORTC, PIN2)      | ADC2                                   |
| Analog Pin A3   | PC3 (PORTC, PIN3)      | ADC3                                   |
| Analog Pin A4   | PC4 (PORTC, PIN4)      | I2C (SDA) / ADC4                       |
| Analog Pin A5   | PC5 (PORTC, PIN5)      | I2C (SCL) / ADC5                       |
| Digital Pin D0  | PD0 (PORTD, PIN0)      | USART (RXD)                            |
| Digital Pin D1  | PD1 (PORTD, PIN1)      | USART (TXD)                            |
| Digital Pin D2  | PD2 (PORTD, PIN2)      | External Interrupt (INT0)              |
| Digital Pin D3  | PD3 (PORTD, PIN3)      | External Interrupt (INT1) / PWM (OC2B) |
| Digital Pin D4  | PD4 (PORTD, PIN4)      | Timer/Counter (XCK/T0)                 |
| Digital Pin D5  | PD5 (PORTD, PIN5)      | PWM (OC0B) / Timer1                    |
| Digital Pin D6  | PD6 (PORTD, PIN6)      | PWM (OC0A) / Analog Comparator         |
| Digital Pin D7  | PD7 (PORTD, PIN7)      | Analog Comparator Input                |
| Digital Pin D8  | PB0 (PORTB, PIN0)      | ICP1 / Clock Output (CLKO)             |
| Digital Pin D9  | PB1 (PORTB, PIN1)      | PWM (OC1A)                             |
| Digital Pin D10 | PB2 (PORTB, PIN2)      | PWM (OC1B) / SPI (SS)                  |
| Digital Pin D11 | PB3 (PORTB, PIN3)      | PWM (OC2A) / SPI (MOSI)                |
| Digital Pin D12 | PB4 (PORTB, PIN4)      | SPI (MISO)                             |
| Digital Pin D13 | PB5 (PORTB, PIN5)      | SPI (SCK) / LED\_BUILTIN               |

---

### **ADC (Analog-to-Digital Converter)**
| **Arduino Pin** | **ATmega328 Pin** | **ADC Channel** | **Other Functionality** |
| --------------- | ----------------- | --------------- | ----------------------- |
| A0              | PC0               | ADC0            | —                       |
| A1              | PC1               | ADC1            | —                       |
| A2              | PC2               | ADC2            | —                       |
| A3              | PC3               | ADC3            | —                       |
| A4              | PC4               | ADC4            | I2C SDA                 |
| A5              | PC5               | ADC5            | I2C SCL                 |

### **Analog Comparator**
| **Arduino Pin** | **ATmega328 Pin** | **Functionality** |
| --------------- | ----------------- | ----------------- |
| D6              | PD6               | AIN0              |
| D7              | PD7               | AIN1              |

### **External Interrupts**
| **Arduino Pin** | **ATmega328 Pin** | **Interrupt** |
| --------------- | ----------------- | ------------- |
| D2              | PD2               | INT0          |
| D3              | PD3               | INT1          |

### **Timers / PWM Outputs**
| **Arduino Pin** | **ATmega328 Pin** | **PWM / Timer** |
| --------------- | ----------------- | ----------------|
| D6              | PD6               | OC0A (PWM)      |
| D5              | PD5               | OC0B (PWM)      |
| D9              | PB1               | OC1A (PWM)      |
| D10             | PB2               | OC1B (PWM)      |
| D11             | PB3               | OC2A (PWM)      |
| D3              | PD3               | OC2B (PWM)      |

| **Arduino Pin** | **ATmega328 Pin** | **Special Timer Function**                 |
| --------------- | ----------------- | ------------------------------------------ |
| D4              | PD4               | **T0** — Timer/Counter0 External Clock     |
| D5              | PD5               | **T1** — Timer/Counter1 External Clock     |
| D8              | PB0               | **ICP1** — Input Capture for Timer1 / CLKO |
| D6              | PD6               | AIN0 — Used in Analog Comparator (shared)  |
| D7              | PD7               | AIN1 — Used in Analog Comparator (shared)  |

### **USART (Serial Communication)**
| **Arduino Pin** | **ATmega328 Pin** | **USART Function** |
| --------------- | ----------------- | ------------------ |
| D0              | PD0               | RXD (Receive)      |
| D1              | PD1               | TXD (Transmit)     |

### **I2C Interface**
| **Arduino Pin** | **ATmega328 Pin** | **I2C Signal** |
| --------------- | ----------------- | -------------- |
| A4              | PC4               | SDA            |
| A5              | PC5               | SCL            |


### **SPI Interface**
| **Arduino Pin** | **ATmega328 Pin** | **SPI Signal** |
| --------------- | ----------------- | -------------- |
| D10             | PB2               | SS             |
| D11             | PB3               | MOSI           |
| D12             | PB4               | MISO           |
| D13             | PB5               | SCK            |

### **Other / General Purpose**
| **Arduino Pin** | **ATmega328 Pin** | **Functionality**                          |
| --------------- | ----------------- | ------------------------------------------ |
| D13             | PB5               | `LED_BUILTIN` / SPI Clock (SCK)            |
| D12             | PB4               | **CKOUT** (System Clock Output) /SPI MISO  |

---

<table>
  <tr>
  <td valign="top">
  
  > [!TIP]  
  > If you're looking to better understand how to navigate and use my GitHub repositories — including exploring their structure, downloading or cloning projects, submitting issues, and asking questions,  
  > everything you need is clearly explained in this video:  
  > [aKaReZa 95 - Programming, Git - PART B](https://youtu.be/zYiUItVFRqQ)  
  > Make sure to check it out!
  
  </td>
    <td width="360" valign="middle" style="padding: 0;">
      <a href="https://youtu.be/zYiUItVFRqQ">
       <img src="https://img.youtube.com/vi/zYiUItVFRqQ/maxresdefault.jpg"
             width="360"
             alt="aKaReZa 95 - Programming, Git - PART B Thumbnail"/>
      </a>
    </td>

  </td>
  </tr>
  <tr>
  <td colspan="2">

  > [!CAUTION]
  > It is absolutely critical that you carefully read every single word of this document, line by line, to ensure you don't miss any details. Nothing can be overlooked.
      
  </td>
  </tr>  
</table>

## Detailed Description
| Aspect               | Description                  |
|----------------------|------------------------------|
| PCB Design Software  | Altium  V24.2.2              |
| PCB Layers           | 2-Layer FR4                  |
| Microcontroller      | ATMEGA328                    |
| Pin Type             | Arduino UNO                  |
| Converter IC         | CH340                        |
| USB Port             | TYPE-C                       |


## Resources
- [Altium Library](https://github.com/aKaReZa75/Altium-Library)  
  ---  
   All PCB designs across all repositories and projects are built using this Altium Designer component library. It contains a wide range of verified footprints, schematic symbols, and 3D models, ensuring consistency and accuracy in PCB designs. If you're working on a new PCB, using this library will save you time and minimize errors.

- [PCB & Electronics Design Training](https://github.com/aKaReZa75/PCB)  
  ---  
  This repository is dedicated to **learning PCB design and electronics from scratch**. It covers everything from circuit theory to practical PCB layout techniques, including routing strategies, best practices, and component placement. Whether you're a beginner or an experienced designer, this resource will help you **improve your PCB design skills and create professional-quality boards**.

- [AVR Microcontroller Training](https://github.com/aKaReZa75/AVR)  
  ---  
  This repository provides a **comprehensive guide to AVR microcontroller programming**, covering everything from the fundamentals to advanced firmware development. Learn about **AVR architecture, peripheral interfacing, timers, interrupts, communication protocols**, and more through hands-on projects and real-world examples. Whether you're just starting or looking to refine your embedded programming skills, this resource will help you master AVR development.

- [Shopping Link](./ShoppingLink.md)  
  ---
  This document provides links to trusted suppliers where you can purchase all the essential components for this project, ensuring quality and reliability.


## Project Videos

```plaintext
Educational Boards
   ├── [aKaReZa 74 - eBoard, ATMEGA328 - PART A]
   │   ├─ Schematic — Voltage reg, UNO pinout, crystal, ADC filter.
   │   ├─ Communication — USBtoTTL + UART indicator.
   │   └─ Features — Auto Prog and library usage.
   │
   ├── [aKaReZa 76 - eBoard, ATMEGA328 - PART B]
   │   ├─ Fixes — Schematic issues and fuse improvements.
   │   ├─ Enhancements — USB Type-C, UART LEDs, voltage divider.
   │   └─ PCB Prep — Placement and routing readiness.
   │
   ├── [aKaReZa 88 - eBoard, ATMEGA328 - PART C]
   │   ├─ Routing — GPIO, USB, MCU, power tracks.
   │   ├─ Optimization — Polygon tool and hierarchical layout.
   │   └─ GitHub — Pull Request and version control.
   │
   └── [aKaReZa 102 - Repair, ATMEGA328 Soldering]
       ├─ Assembly — Voltage tests, MCU soldering, USB Type-C.
       ├─ Conversion — CH340 setup and verification.
       └─ Testing — Section-by-section validation.
```

<table style="border-collapse: collapse;">
  <tr>
    <td valign="top" style="padding: 0 10px;">
      <h3 style="margin: 0;">
        <a href="https://youtu.be/-ttv7IQRaWA">aKaReZa 74 – eBoard, ATMEGA328 - PART A</a>
      </h3>
      <p style="margin: 8px 0 0;">
        This video is the first in a new series called eBoard, which stands for Educational Boards. In this video, we design the schematic for an educational header board specifically for the ATMEGA328 microcontroller used in the channel's tutorials.
      </p>
    </td>
    <td width="360" valign="top" style="padding: 0;">
      <a href="https://youtu.be/-ttv7IQRaWA">
        <img src="https://img.youtube.com/vi/-ttv7IQRaWA/maxresdefault.jpg"
             width="360"
             alt="aKaReZa 74 – eBoard, ATMEGA328 - PART A Thumbnail"/>
      </a>
    </td>
  </tr>

  <tr>
    <td valign="top" style="padding: 0 10px;">
      <h3 style="margin: 0;">
        <a href="https://youtu.be/Ipy6SqzdZnI">aKaReZa 76 – eBoard, ATMEGA328 - PART B</a>
      </h3>
      <p style="margin: 8px 0 0;">
        In this video, we fix a few issues in the schematic, upgrade and change several sections, and then transfer all components to the PCB. We arrange the components and prepare them for routing.
      </p>
    </td>
    <td width="360" valign="top" style="padding: 0;">
      <a href="https://youtu.be/Ipy6SqzdZnI">
        <img src="https://img.youtube.com/vi/Ipy6SqzdZnI/maxresdefault.jpg"
             width="360"
             alt="aKaReZa 76 – eBoard, ATMEGA328 - PART B Thumbnail"/>
      </a>
    </td>
  </tr>

  <tr>
    <td valign="top" style="padding: 0 10px;">
      <h3 style="margin: 0;">
        <a href="https://youtu.be/WwyNDgpCwrc">aKaReZa 88 – eBoard, ATMEGA328 - PART C</a>
      </h3>
      <p style="margin: 8px 0 0;">
        In this video, we complete the routing for the ATMEGA328 educational board and get familiar with related tips.
      </p>
    </td>
    <td width="360" valign="top" style="padding: 0;">
      <a href="https://youtu.be/WwyNDgpCwrc">
        <img src="https://img.youtube.com/vi/WwyNDgpCwrc/maxresdefault.jpg"
             width="360"
             alt="aKaReZa 88 – eBoard, ATMEGA328 - PART C Thumbnail"/>
      </a>
    </td>
  </tr>

  <tr>
    <td valign="top" style="padding: 0 10px;">
      <h3 style="margin: 0;">
        <a href="https://youtu.be/j-jOPXrMTt0">aKaReZa 102 – Repair, ATMEGA328 Soldering</a>
      </h3>
      <p style="margin: 8px 0 0;">
        Step-by-step soldering of an ATMEGA328-based board, covering power input, voltage regulators (12V, 5V, 3.3V), microcontroller placement, USB Type-C port installation, CH340 for USB-to-UART conversion, final connections, bootloader programming, and full board testing to ensure proper functionality.
      </p>
    </td>
    <td width="360" valign="top">
      <a href="https://youtu.be/j-jOPXrMTt0">
        <img src="https://img.youtube.com/vi/j-jOPXrMTt0/maxresdefault.jpg"
             width="360"
             alt="aKaReZa 102 – Repair, ATMEGA328 Soldering Thumbnail"/>
      </a>
    </td>
  </tr>

</table>


# 💻 How to Use Git and GitHub
To access the repository files and save them on your computer, there are two methods available:
1. **Using Git Bash and Cloning the Repository**
   - This method is more suitable for advanced users and those familiar with command-line tools.
   - By using this method, you can easily receive updates for the repository.

2. **Downloading the Repository as a ZIP file**
   - This method is simpler and suitable for users who are not comfortable with command-line tools.
   - Note that with this method, you will not automatically receive updates for the repository and will need to manually download any new updates.
     
## Clone using the URL.
First, open **Git Bash** :
-  Open the folder in **File Explorer** where you want the library to be stored.
-  **Right-click** inside the folder and select the option **"Open Git Bash here"** to open **Git Bash** in that directory.

![open Git Bash](Images/Step0.png)

> [!NOTE] 
> If you do not see the "Open Git Bash here" option, it means that Git is not installed on your system.  
> You can download and install Git from [this link](https://git-scm.com/downloads).  
> For a tutorial on how to install and use Git, check out [this video](https://youtu.be/BsykgHpmUt8).
  
-  Once **Git Bash** is open, run the following command to clone the repository:

 ```bash
git clone https://github.com/aKaReZa75/eBoard_ATMEGA328.git
```
- You can copy the above command by either:
- Clicking on the **Copy** button on the right of the command.
- Or select the command text manually and press **Ctrl + C** to copy.
- To paste the command into your **Git Bash** terminal, use **Shift + Insert**.

![Clone the Repository](Images/Step1.png)

- Then, press Enter to start the cloning operation and wait for the success message to appear.

![Open the Library File](Images/Step2.png)

> [!IMPORTANT]
> Please keep in mind that the numbers displayed in the image might vary when you perform the same actions.  
> This is because repositories are continuously being updated and expanded. Nevertheless, the overall process remains unchanged.

> [!NOTE]
> Advantage of Cloning the Repository:  
> - **Receiving Updates:** By cloning the repository, you can easily and automatically receive new updates.  
> - **Version Control:** Using Git allows you to track changes and revert to previous versions.  
> - **Team Collaboration:** If you are working on a project with a team, you can easily sync changes from team members and collaborate more efficiently.  

## Download Zip
If you prefer not to use Git Bash or the command line, you can download the repository directly from GitHub as a ZIP file.  
Follow these steps:  
1. Navigate to the GitHub repository page and Locate the Code button:
- On the main page of the repository, you will see a green Code button near the top right corner.

2. Download the repository:
- Click the Code button to open a dropdown menu.
- Select Download ZIP from the menu.

  ![Download Zip](Images/Step7.png)  

3. Save the ZIP file:
- Choose a location on your computer to save the ZIP file and click Save.

4. Extract the ZIP file:
- Navigate to the folder where you saved the ZIP file.
- Right-click on the ZIP file and select Extract All... (Windows) or use your preferred extraction tool.
- Choose a destination folder and extract the contents.

5. Access the repository:
- Once extracted, you can access the repository files in the destination folder.

> [!IMPORTANT]
> - No Updates: Keep in mind that downloading the repository as a ZIP file does not allow you to receive updates.    
>   If the repository is updated, you will need to download it again manually.  
> - Ease of Use: This method is simpler and suitable for users who are not comfortable with Git or command-line tools.

# 📝 How to Ask Questions
If you have any questions or issues, you can raise them through the **"Issues"** section of this repository. Here's how you can do it:  

1. Navigate to the **"Issues"** tab at the top of the repository page.  

  ![Issues](Images/Step3.png)

2. Click on the **"New Issue"** button.  
   
  ![New Issue](Images/Step4.png)

3. In the **Title** field, write a short summary of your issue or question.  

4. In the "Description" field, detail your question or issue as thoroughly as possible. You can use text formatting, attach files, and assign the issue to someone if needed. You can also use text formatting (like bullet points or code snippets) for better readability.  

5. Optionally, you can add **labels**, **type**, **projects**, or **milestones** to your issue for better categorization.  

6. Click on the **"Submit new issue"** button to post your question or issue.
   
  ![Submeet New Issue](Images/Step5.png)

I will review and respond to your issue as soon as possible. Your participation helps improve the repository for everyone!  

> [!TIP]
> - Before creating a new issue, please check the **"Closed"** section to see if your question has already been answered.  
>   ![Closed section](Images/Step6.png)  
> - Write your question clearly and respectfully to ensure a faster and better response.  
> - While the examples provided above are in English, feel free to ask your questions in **Persian (فارسی)** as well.  
> - There is no difference in how they will be handled!  

> [!NOTE]
> Pages and interfaces may change over time, but the steps to create an issue generally remain the same.

# 🤝 Contributing to the Repository
To contribute to this repository, please follow these steps:
1. **Fork the Repository**  
2. **Clone the Forked Repository**  
3. **Create a New Branch**  
4. **Make Your Changes**  
5. **Commit Your Changes**  
6. **Push Your Changes to Your Forked Repository**  
7. **Submit a Pull Request (PR)**  

> [!NOTE]
> Please ensure your pull request includes a clear description of the changes you’ve made.
> Once submitted, I will review your contribution and provide feedback if necessary.

# 🌟 Support Me
If you found this repository useful:
- Subscribe to my [YouTube Channel](https://www.youtube.com/@aKaReZa75).
- Share this repository with others.
- Give this repository and my other repositories a star.
- Follow my [GitHub account](https://github.com/aKaReZa75).

# 📜 License
This project is licensed under the GPL-3.0 License. This license grants you the freedom to use, modify, and distribute the project as long as you:
- Credit the original authors: Give proper attribution to the original creators.
- Disclose source code: If you distribute a modified version, you must make the source code available under the same GPL license.
- Maintain the same license: When you distribute derivative works, they must be licensed under the GPL-3.0 too.
- Feel free to use it in your projects, but make sure to comply with the terms of this license.
  
# ✉️ Contact Me
Feel free to reach out to me through any of the following platforms:
- 📧 [Email: aKaReZa75@gmail.com](mailto:aKaReZa75@gmail.com)
- 🎥 [YouTube: @aKaReZa75](https://www.youtube.com/@aKaReZa75)
- 💼 [LinkedIn: @akareza75](https://www.linkedin.com/in/akareza75)
