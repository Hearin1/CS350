END OF CLASS Reflection:

Questions that I was trying to asnwer: 
1. Summarize the project and what problem it was solving.
2. What did you do particularly well?
3. Where could you improve?
4. What tools and/or resources are you adding to your support network?
5. What skills from this project will be particularly transferable to other projects and/or course work?
6. How did you make this project maintainable, readable, and adaptable?

  Throughout the course, I had a lot of opportunity to develop and refine a range of skills while working with systems architectures and hardware control. The two project artifacts I selected for my portfolio are the Thermostat Control System and the Morse Code LED Translator. These projects best reflect my ability to interface software with physical components, implement structured software design, and reason through the constraints and capabilities of hardware systems.

  The Thermostat Control System project tackled the challenge of using a Raspberry Pi to monitor environmental data and control output devices (LEDs) based on user inputs and system logic. It addressed the real-world problem of managing temperature using hardware-software integration. The Morse Code project, on the other hand, showcased my ability to manipulate timing and GPIO control to transmit text in a visual medium—a task that required both creativity and technical precision.

  One area where I feel I excelled was in structuring the code to be readable, modular, and maintainable. I tried to consistently use clear naming conventions, broke down functions logically, and documented behavior where necessary. I also ensured that the hardware setup and codebase could be easily understood by others, which is a key part of writing adaptable code for embedded systems.

  At the same time, there are areas I could improve. So many areas.... For instance, I initially struggled with debugging GPIO-related issues, especially when working remotely via SSH. These setbacks taught me to slow down and verify each component in isolation before assuming higher-level logic was at fault. In future projects, I plan to invest more time in test planning and hardware setup validation.

  I’ve added several important tools to my support network, including the RPi.GPIO and Adafruit_DHT Python libraries, GitHub for version control and sharing, and online communities like Stack Overflow and the Raspberry Pi forums. The raaspberry pi forums were where I really took advantage. I was there for almost every question I was facing. These tools not only supported my learning but will also be essential in future embedded systems or IoT work.

  Many of the skills I practiced—such as using UART communication, interpreting sensor data, and managing software-hardware interactions—are directly transferable to both coursework and real-world projects. I also improved my ability to reason about performance trade-offs when working within the constraints of small-scale hardware.

  Ultimately, I focused on making my projects maintainable and adaptable by writing modular code and including clear documentation. I designed the scripts in a way that allows future enhancements, such as expanding to multiple sensors or different output mechanisms, without requiring a complete rewrite. This forward-thinking approach ensures my work remains useful not just as a snapshot of what I’ve done, but as a foundation I can build upon in more advanced systems.








FINAL PROJECT Written Portion:

  The development of the smart thermostat prototype provided a hands-on opportunity to integrate software control with physical hardware, emphasizing the principles of embedded systems and state machine design. Beginning with basic GPIO interaction and I2C sensor integration, the project progressively evolved to include UART serial communication, LCD feedback, and responsive LED indicators. Through this process, I gained a deeper understanding of how a microcontroller system interacts with multiple peripherals in real time while managing user input, output display, and data transmission effectively. 

  The system was designed to cycle between three states: off, heating, and cooling. These states were managed via a finite state machine implemented in Python. A single button toggled the system between states, while two additional buttons allowed the user to adjust the thermostat’s set temperature. Real-time temperature was acquired using an AHT20 temperature and humidity sensor via the I2C protocol, and the current mode and temperature readings were displayed on a 16x2 LCD. Feedback was also provided through red and blue LEDs: when in heating or cooling mode, the respective LED would either remain solid or pulse depending on whether the target temperature had been reached. I had a lot of problems with this. The LEDs would just not work for a while. After a lot of debugging, I was finally able to get it. 

  A major challenge was managing the hardware-level feedback behavior, particularly with PWM-based LED pulsing. Ensuring compatibility across Python versions and hardware-specific GPIO limitations required several iterations and workarounds. Additionally, synchronizing the LCD updates with temperature reads and UART transmissions every few seconds without creating thread conflicts or timing issues required careful threading and flow control. Despite these challenges, the final result met all functional requirements and performed consistently under test conditions. 

  Looking ahead to the next phase of development—transitioning the thermostat to a cloud-connected device—requires evaluating potential hardware platforms for production use. Raspberry Pi is a strong contender due to its compatibility with the existing prototype and built-in Wi-Fi. However, Microchip microcontrollers, such as the PIC32 series, offer lower power consumption and are widely used in embedded products. Freescale (now part of NXP Semiconductors) also offers advanced microcontrollers like the Kinetis series with integrated Wi-Fi and extensive peripheral support. Ultimately, the best choice will depend on factors such as cost, power efficiency, and required memory. 

  Based on this project’s requirements—support for I2C, GPIO, UART, Wi-Fi, and sufficient flash/RAM for the Python logic—the Raspberry Pi remains the most straightforward option for a quick product launch, particularly in low-volume or prototype settings. However, for embedded efficiency, a Microchip or NXP solution with native cloud connectivity and lower power draw may prove more optimal. This project has been instrumental in preparing me to assess these architectural tradeoffs in a practical engineering context. I will be still using my Raspberry pi in the future. I am not sure about the bread board, but the rest I should be using.  
