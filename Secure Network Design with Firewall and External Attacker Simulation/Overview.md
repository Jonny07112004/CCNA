## Lab Topology Overview: Network Security & Attack Simulation

This lab simulates **secure communication between two internal networks** while introducing an **external attacker machine** to demonstrate **basic network security concepts, firewall placement, and traffic control**.

The topology is designed to help understand how **routers, switches, and firewalls protect internal assets from external threats**, which is highly relevant for **Networking and SOC internship roles**.

----------

## Topology Breakdown

### Internal Client Network (Left LAN)

-   **PC0, PC1** – Internal client hosts
    
-   **Switch0** – Layer 2 switch for local connectivity
    
-   **Router1** – Default gateway routing traffic outside the LAN
    

This segment represents a **typical internal user network**.

----------

### Security & WAN Segment

-   **ASA0 (Firewall)** – Filters traffic between the internal LAN and the external network
    
-   **Internet (Cloud Router)** – Simulates the public Internet
    
-   **Laptop0 (Attacker Machine)** – Represents an external attacker attempting to probe or access internal resources
    

The attacker machine is used to practice:

-   Understanding attack paths
    
-   Identifying exposed services
    
-   Observing firewall behavior
    
-   Analyzing allowed vs blocked traffic
    

----------

### Protected Server Network (Right LAN)

-   **Router2** – Routes traffic from the WAN to the server network
    
-   **ASA1 (Firewall)** – Protects internal servers from unauthorized access
    
-   **Switch1** – Connects internal servers
    
-   **Server0, Server1** – Internal services (e.g., Web / Application servers)
    

This simulates a **secured server or data-center network**.

----------

## Key Concepts Practiced

-   Network segmentation and isolation
    
-   Perimeter firewall deployment
    
-   Secure client-to-server communication
    
-   External attack simulation
    
-   Traffic inspection and filtering
    
-   Understanding trust boundaries
    

----------

## Skills Demonstrated

-   Ability to design and analyze secure network topologies
    
-   Understanding of attacker vs internal traffic flows
    
-   Foundational security awareness for networking roles
    
-   Hands-on experience relevant to **CCNA, SOC, and cybersecurity internships**
    

----------

## Learning Objective

The objective of this lab is to:

-   Visualize how attackers interact with network boundaries
    
-   Understand how firewalls protect internal assets
    
-   Build security-aware networking fundamentals
    

----------

## Ethical Notice

This lab is conducted in a **controlled, simulated environment** for **educational purposes only**. No real-world systems are targeted.## Lab Topology Overview: Network Security & Attack Simulation

This lab simulates **secure communication between two internal networks** while introducing an **external attacker machine** to demonstrate **basic network security concepts, firewall placement, and traffic control**.

The topology is designed to help understand how **routers, switches, and firewalls protect internal assets from external threats**, which is highly relevant for **Networking and SOC internship roles**.

----------

## Topology Breakdown

### Internal Client Network (Left LAN)

-   **PC0, PC1** – Internal client hosts
    
-   **Switch0** – Layer 2 switch for local connectivity
    
-   **Router1** – Default gateway routing traffic outside the LAN
    

This segment represents a **typical internal user network**.

----------

### Security & WAN Segment

-   **ASA0 (Firewall)** – Filters traffic between the internal LAN and the external network
    
-   **Internet (Cloud Router)** – Simulates the public Internet
    
-   **Laptop0 (Attacker Machine)** – Represents an external attacker attempting to probe or access internal resources
    

The attacker machine is used to practice:

-   Understanding attack paths
    
-   Identifying exposed services
    
-   Observing firewall behavior
    
-   Analyzing allowed vs blocked traffic
    

----------

### Protected Server Network (Right LAN)

-   **Router2** – Routes traffic from the WAN to the server network
    
-   **ASA1 (Firewall)** – Protects internal servers from unauthorized access
    
-   **Switch1** – Connects internal servers
    
-   **Server0, Server1** – Internal services (e.g., Web / Application servers)
    

This simulates a **secured server or data-center network**.

----------

## Key Concepts Practiced

-   Network segmentation and isolation
    
-   Perimeter firewall deployment
    
-   Secure client-to-server communication
    
-   External attack simulation
    
-   Traffic inspection and filtering
    
-   Understanding trust boundaries
    

----------

## Skills Demonstrated

-   Ability to design and analyze secure network topologies
    
-   Understanding of attacker vs internal traffic flows
    
-   Foundational security awareness for networking roles
    
-   Hands-on experience relevant to **CCNA, SOC, and cybersecurity internships**
    

----------

## Learning Objective

The objective of this lab is to:

-   Visualize how attackers interact with network boundaries
    
-   Understand how firewalls protect internal assets
    
-   Build security-aware networking fundamentals
    

----------

## Ethical Notice

This lab is conducted in a **controlled, simulated environment** for **educational purposes only**. No real-world systems are targeted.