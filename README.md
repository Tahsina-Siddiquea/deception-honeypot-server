# Deception Honeypot Server

## Project Introduction

The Deception Honeypot Server is a defensive cybersecurity simulation designed to observe, capture, and analyze malicious authentication attempts in a controlled environment.

This project recreates the behavioral dynamics of exposed network services by deploying a deceptive authentication endpoint that attracts unauthorized access attempts. By logging attacker interactions and analyzing credential usage patterns, the system provides practical insights into real-world intrusion strategies.

The implementation reflects foundational concepts used in modern security operations centers (SOC), threat research labs, and incident response workflows.

## Core Objectives

* Simulate exposed authentication services to attract malicious actors
* Monitor and record unauthorized connection attempts
* Capture credential-based attack patterns
* Identify brute-force attack behaviour
* Generate structured attack intelligence reports
* Demonstrate practical defensive cybersecurity engineering


## Functional Highlights

* TCP-based honeypot server simulating SSH authentication
* Concurrent attacker handling using multi-threading
* Real-time credential capture and event logging
* Timestamped attack session tracking
* Frequency-based brute-force detection mechanism
* Automated threat statistics generation
* Lightweight architecture suitable for lab deployment


## System Architecture

The honeypot operates as a TCP server that listens for incoming connections on a designated port.
Upon connection, the system mimics a legitimate authentication interface to observe attacker behavior.

Captured attack data includes:

* Source IP address
* Login attempt timestamps
* Username and password attempts
* Connection frequency patterns
* Suspicious brute-force indicators

Collected data is then processed to generate a structured security analysis report.


## Project Structure
```
honeypot/
│
├── honeypot.py          → Main honeypot server logic
├── logger.py            → Attack logging and statistical analysis engine
├── report.py            → Security report generation module
├── attacker_test.py     → Attack simulation client  
└── README.MD
```

## Technologies Used

* Python Socket Programming
* Multi-threading (concurrent client handling)
* Network traffic interaction simulation
* Defensive logging and incident analysis
* Basic intrusion detection logic


## How the Honeypot Works

1. The server listens for incoming TCP connections.
2. When an attacker connects, the system displays a fake SSH login banner.
3. The attacker attempts to enter credentials.
4. The honeypot captures and stores:

	* IP address
	* username attempts
	* password attempts
	* connection frequency
5. The logger analyzes patterns to detect brute-force activity.
6. A structured incident report is generated summarizing attack intelligence.


## Example Terminal Output

### Running the Honeypot
```
$ python honeypot.py

Honeypot running on port 2222 (SSH simulation)
Connection attempt detected
IP: 192.168.1.50
Timestamp: 2026-03-05 20:15:32
Credential attempt captured
Username: admin
Password: password123
```

### Generated Security Report
```
===== HONEYPOT ATTACK REPORT =====

Total connections: 18
Unique IPs: 3
Top username tried: admin
Top password tried: password123

Possible brute-force attackers:
192.168.1.50 → 10 attempts
```

## Performance Considerations

The system is designed to operate efficiently in resource-constrained environments:

* Low memory footprint due to minimal state storage
* Concurrent connection processing through lightweight threading
* Rapid event logging without heavy external dependencies
* Suitable for academic security labs and controlled training networks


## Security & Ethical Deployment

This honeypot simulation is intended strictly for:

* Cybersecurity education and training
* Defensive research experimentation
* Intrusion detection concept validation
* Academic demonstration of threat monitoring techniques

Deployment must remain within authorized environments to avoid unintended legal or ethical implications.

## Educational Value

Through this project, the following competencies are demonstrated:

* Realistic attack surface simulation
* Practical intrusion monitoring methodology
* Defensive programming mindset
* Security telemetry collection techniques
* Incident analysis and reporting fundamentals
* Introduction to threat intelligence engineering


## Author

Developed as part of an independent cybersecurity learning initiative focused on hands-on defensive security engineering and network threat observation techniques.


## License

This project is released for educational and research use.
Users are responsible for ensuring deployment complies with applicable policies and regulations.
