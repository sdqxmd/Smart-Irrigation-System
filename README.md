<!-- ANIMATED HEADER -->
<p align="center">
  <img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:081C15,50:2D6A4F,100:52B788&height=160&section=header&text=IoT%20for%20Smarter%20Irrigation&fontSize=30&fontColor=FFFFFF&animation=twinkling&fontAlignY=35" alt="IoT for smarter irrigation" />
</p>

<h1 align="center">🌱 Smart Irrigation System</h1>

<h3 align="center">
  ESP32 · Environmental Monitoring · Fuzzy Logic · Solar Power
</h3>

<p align="center">
  <img width="100%" src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=23&duration=3000&pause=1200&color=52B788&center=true&vCenter=true&width=850&height=55&lines=Sense+the+soil.;Monitor+the+environment.;Control+irrigation+with+fuzzy+logic.;Connect+through+ESP32+Wi-Fi." alt="Sense the soil. Monitor the environment. Control irrigation with fuzzy logic. Connect through ESP32 Wi-Fi." />
</p>

<p align="center">
  <b>Connecting soil, sensors, and irrigation through embedded intelligence.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Controller-ESP32-2D6A4F?style=for-the-badge&logo=espressif&logoColor=white&labelColor=081C15" alt="Controller: ESP32" />
  <img src="https://img.shields.io/badge/Control-Fuzzy_Logic-40916C?style=for-the-badge&labelColor=081C15" alt="Control: fuzzy logic" />
  <img src="https://img.shields.io/badge/Connectivity-Wi--Fi-52B788?style=for-the-badge&labelColor=081C15" alt="Connectivity: Wi-Fi" />
  <img src="https://img.shields.io/badge/Power-Solar_%2B_Battery-74C69D?style=for-the-badge&labelColor=081C15" alt="Power: solar and battery" />
</p>

<p align="center">
  <a href="#overview">Overview</a> ·
  <a href="#features">Features</a> ·
  <a href="#system-overview">System Overview</a> ·
  <a href="#prototype">Prototype</a> ·
  <a href="#hardware-components">Hardware</a> ·
  <a href="#pin-connections">Connections</a> ·
  <a href="#applications">Applications</a>
</p>

---

<h2 align="center">Overview</h2>

<p align="center">
  An <b>ESP32-based IoT Smart Irrigation System</b> that combines
  environmental sensing, automatic irrigation control,
  and wireless monitoring for smart farming applications.
</p>

<p align="center">
  The system monitors <b>soil moisture, temperature, humidity,
  soil pH, and solar panel voltage</b>.
  It uses <b>fuzzy logic</b> for automatic irrigation control
  and <b>ESP32 Wi-Fi</b> for wireless monitoring.
</p>

<p align="center">
  <code>SENSE</code>
  &nbsp; → &nbsp;
  <code>PROCESS</code>
  &nbsp; → &nbsp;
  <code>CONTROL</code>
  &nbsp; → &nbsp;
  <code>MONITOR</code>
</p>

---

<h2 align="center">Features</h2>

<table align="center">
  <tr>
    <td width="50%" align="center" valign="top">
      <h3>🌱 Soil Monitoring</h3>
      <p>
        Monitor soil moisture and pH to observe
        conditions around the irrigation area.
      </p>
      <p>
        <code>Soil Moisture</code>
        <code>Soil pH</code>
      </p>
    </td>
    <td width="50%" align="center" valign="top">
      <h3>🌡️ Environmental Sensing</h3>
      <p>
        Measure temperature and humidity
        using the DHT11 sensor.
      </p>
      <p>
        <code>Temperature</code>
        <code>Humidity</code>
      </p>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center" valign="top">
      <h3>🧠 Automatic Irrigation</h3>
      <p>
        Apply fuzzy logic for irrigation control,
        with a relay module switching the water pump.
      </p>
      <p>
        <code>Fuzzy Logic</code>
        <code>Relay Control</code>
      </p>
    </td>
    <td width="50%" align="center" valign="top">
      <h3>📡 Wireless Monitoring</h3>
      <p>
        Use the ESP32's Wi-Fi connectivity
        for wireless monitoring of system readings.
      </p>
      <p>
        <code>ESP32</code>
        <code>Wi-Fi</code>
        <code>IoT</code>
      </p>
    </td>
  </tr>
</table>

<p align="center">
  ☀️ <b>Solar panel voltage monitoring</b>
  &nbsp; · &nbsp;
  🔋 <b>12V battery</b>
  &nbsp; · &nbsp;
  🖥️ <b>OLED display</b>
</p>

---

<h2 align="center">System Overview</h2>

<p align="center">
  <b>From sensor measurements to irrigation control.</b>
</p>

<!-- Functional overview; GPIO assignments are listed below. -->
```mermaid
flowchart TD
    DHT["DHT11"]
    SOIL["Soil moisture sensor"]
    PH["pH sensor"]
    INA["INA219"]

    ESP["ESP32: monitoring and fuzzy control"]

    OLED["OLED display"]
    WIFI["Wi-Fi monitoring"]
    RELAY["Relay module"]
    PUMP["Water pump"]

    DHT --> ESP
    SOIL --> ESP
    PH --> ESP
    INA --> ESP

    ESP --> OLED
    ESP --> WIFI
    ESP --> RELAY
    RELAY --> PUMP

    classDef sensor fill:#1B4332,stroke:#74C69D,color:#FFFFFF;
    classDef controller fill:#2D6A4F,stroke:#B7E4C7,color:#FFFFFF;
    classDef output fill:#081C15,stroke:#52B788,color:#FFFFFF;

    class DHT,SOIL,PH,INA sensor;
    class ESP controller;
    class OLED,WIFI,RELAY,PUMP output;
```

<div align="center">
  <table align="center">
    <thead>
      <tr>
        <th align="center">Stage</th>
        <th align="center">Role</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td align="center">🌱 <b>Sense</b></td>
        <td align="center">
          Collect soil, environmental, and solar panel voltage readings.
        </td>
      </tr>
      <tr>
        <td align="center">🧠 <b>Process</b></td>
        <td align="center">
          Process measurements and apply fuzzy logic for irrigation control.
        </td>
      </tr>
      <tr>
        <td align="center">💧 <b>Control</b></td>
        <td align="center">
          Operate the water pump through the relay module.
        </td>
      </tr>
      <tr>
        <td align="center">📡 <b>Monitor</b></td>
        <td align="center">
          Support wireless monitoring through ESP32 Wi-Fi.
        </td>
      </tr>
    </tbody>
  </table>
</div>

---

<h2 align="center">Prototype</h2>

<p align="center">
  <b>From sensor readings to a working irrigation setup.</b>
</p>

<p align="center">
  <a href="https://raw.githubusercontent.com/sdqxmd/Smart-Irrigation-System/main/Images/IMG20260418163030.jpg.jpeg">
    <img height="420" src="https://raw.githubusercontent.com/sdqxmd/Smart-Irrigation-System/main/Images/IMG20260418163030.jpg.jpeg" alt="Smart irrigation prototype with solar panel, ESP32, sensors, and pump" />
  </a>
</p>

<p align="center">
  <sub>
    Solar panel · ESP32 controller · Sensor integration · Irrigation hardware
    <br />
    Click the image to view it at full size.
  </sub>
</p>

---

<h2 align="center">Hardware Components</h2>

<p align="center">
  <img src="https://skillicons.dev/icons?i=arduino,cpp&theme=dark" alt="Embedded development with Arduino and C++" />
</p>

<div align="center">
  <table align="center">
    <thead>
      <tr>
        <th align="center">Component</th>
        <th align="center">Purpose</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td align="center"><b>ESP32</b></td>
        <td align="center">Main controller and Wi-Fi connectivity</td>
      </tr>
      <tr>
        <td align="center"><b>DHT11 Sensor</b></td>
        <td align="center">Temperature and humidity sensing</td>
      </tr>
      <tr>
        <td align="center"><b>RC-A-4079 Soil Moisture Sensor</b></td>
        <td align="center">Soil moisture sensing</td>
      </tr>
      <tr>
        <td align="center"><b>INA219 Voltage/Current Sensor</b></td>
        <td align="center">Electrical sensing for solar panel monitoring</td>
      </tr>
      <tr>
        <td align="center"><b>pH Sensor</b></td>
        <td align="center">Soil pH measurement</td>
      </tr>
      <tr>
        <td align="center"><b>Relay Module</b></td>
        <td align="center">Water pump switching</td>
      </tr>
      <tr>
        <td align="center"><b>Water Pump</b></td>
        <td align="center">Water delivery for irrigation</td>
      </tr>
      <tr>
        <td align="center"><b>OLED Display</b></td>
        <td align="center">Local display interface</td>
      </tr>
      <tr>
        <td align="center"><b>Buck Converter</b></td>
        <td align="center">DC voltage step-down</td>
      </tr>
      <tr>
        <td align="center"><b>Solar Panel</b></td>
        <td align="center">Solar energy generation</td>
      </tr>
      <tr>
        <td align="center"><b>12V Battery</b></td>
        <td align="center">Energy storage</td>
      </tr>
    </tbody>
  </table>
</div>

---

<h2 align="center">Pin Connections</h2>

<p align="center">
  <b>ESP32 GPIO assignments</b>
</p>

<div align="center">
  <table align="center">
    <thead>
      <tr>
        <th align="center">Component / Signal</th>
        <th align="center">ESP32 Pin</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td align="center">DHT11 Sensor</td>
        <td align="center"><code>GPIO 4</code></td>
      </tr>
      <tr>
        <td align="center">Soil Moisture Sensor</td>
        <td align="center"><code>GPIO 34</code></td>
      </tr>
      <tr>
        <td align="center">pH Sensor</td>
        <td align="center"><code>GPIO 35</code></td>
      </tr>
      <tr>
        <td align="center">INA219 — SDA</td>
        <td align="center"><code>GPIO 21</code></td>
      </tr>
      <tr>
        <td align="center">INA219 — SCL</td>
        <td align="center"><code>GPIO 22</code></td>
      </tr>
      <tr>
        <td align="center">OLED Display — SDA</td>
        <td align="center"><code>GPIO 21</code></td>
      </tr>
      <tr>
        <td align="center">OLED Display — SCL</td>
        <td align="center"><code>GPIO 22</code></td>
      </tr>
      <tr>
        <td align="center">Relay Module</td>
        <td align="center"><code>GPIO 26</code></td>
      </tr>
    </tbody>
  </table>
</div>

<p align="center">
  <sub>
    The INA219 and OLED share the I²C connections:
    <b>SDA → GPIO 21</b> and <b>SCL → GPIO 22</b>.
  </sub>
</p>

---

<h2 align="center">Applications</h2>

<p align="center">
  🌾 <b>Smart Agriculture</b>
  &nbsp; · &nbsp;
  💧 <b>Automated Irrigation</b>
  &nbsp; · &nbsp;
  🎯 <b>Precision Farming</b>
</p>

<p align="center">
  🚰 <b>Water Management</b>
  &nbsp; · &nbsp;
  📡 <b>IoT-Based Monitoring Systems</b>
</p>

---

<h2 align="center">Learning Outcomes</h2>

<div align="center">
  <table align="center">
    <thead>
      <tr>
        <th align="center">Area</th>
        <th align="center">Skills Developed</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td align="center">🔌 <b>Embedded Programming</b></td>
        <td align="center">ESP32 programming and embedded system design</td>
      </tr>
      <tr>
        <td align="center">🌡️ <b>Sensor Integration</b></td>
        <td align="center">Sensor interfacing and calibration</td>
      </tr>
      <tr>
        <td align="center">🧠 <b>Control Logic</b></td>
        <td align="center">Fuzzy logic control and irrigation automation</td>
      </tr>
      <tr>
        <td align="center">📡 <b>IoT Development</b></td>
        <td align="center">Wireless data monitoring and connected system development</td>
      </tr>
      <tr>
        <td align="center">🌾 <b>System Integration</b></td>
        <td align="center">Combining sensors, control, and actuation for smart farming</td>
      </tr>
    </tbody>
  </table>
</div>

---

<h2 align="center">Author</h2>

<p align="center">
  <b>Mohammad Sadique</b><br />
  Electrical Engineering · Jamia Millia Islamia, New Delhi
</p>

<p align="center">
  <a href="https://github.com/sdqxmd">
    <img src="https://img.shields.io/badge/GitHub-sdqxmd-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub: sdqxmd" />
  </a>
  <a href="https://www.linkedin.com/in/mdsdq/">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge" alt="LinkedIn" />
  </a>
  <a href="mailto:mohdsadique6970942@gmail.com">
    <img src="https://img.shields.io/badge/Email-2D6A4F?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
  </a>
</p>

<p align="center">
  <b>🌱 Observe the environment. Understand the data. Automate with purpose.</b>
</p>

<p align="center">
  <a href="#overview">Back to overview ↑</a>
</p>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:081C15,50:2D6A4F,100:52B788&height=110&section=footer" alt="Green wave footer" />
