


# 📹 Video: What is CI/CD Pipeline? | Simply Explained by Shradha Ma'am

**Channel:** Apna College

**Instructor:** Shradha Khapra

**Link:** [Watch on YouTube](http://www.youtube.com/watch?v=gLptmcuCx6Q)

### 📝 Executive Summary

In modern Agile and DevOps frameworks, high-scale applications (e.g., e-commerce platforms) require frequent iterations, bug fixes, and feature expansions [[00:45](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=45)]. Performing these integration and hosting steps manually leads to **Integration Hell**, deployment delays, and human errors [[04:21](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=261), [07:59](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=479)]. **CI/CD (Continuous Integration / Continuous Delivery)** automates these phases using structured YAML/automation scripts, allowing teams to ship safe, performant code continuously with zero baseline downtime [[04:53](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=293), [10:35](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=635)].

### 🚀 Key Highlights & "Aha!" Moments

- **Continuous Integration (CI) Focus:** Automates the _Build_ and _Test_ milestones of the Software Development Life Cycle (SDLC) [[05:18](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=318)]. Every single code commit triggers an automated compilation check to catch errors instantly [[10:08](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=608)].
    
- **Continuous Delivery vs. Deployment (CD):** * **Continuous Delivery:** Deploys code automatically to a staging environment, but requires a _manual human approval gate_ before pushing updates live to production [[05:53](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=353)].
    
    - **Continuous Deployment:** Completely human-free automation. Code propagates from testing straight onto production instances if all health criteria clear [[06:25](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=385)].
        
- **The Artifact Concept:** The primary output of a CI pipeline is a deployable "Artifact" (e.g., a `.apk` file for Android or packaged binaries carrying all necessary application libraries and resources) [[01:56](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=116)].
    

### 🔍 System Breakdown: CI/CD Pipeline Architecture

#### 1. Continuous Integration (CI) Phase

When a developer commits modifications locally and pushes them to a remote tracking branch [[01:27](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=87)]:

- **Build Stage:** The automation engine assembles the application code along with its required dependencies into a unified executable file or image package [[01:56](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=116)].
    
- **Test Stage:** Re-runs the entire verification suite automatically [[02:24](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=144)]:
    
    - _Unit Testing:_ Validates individual software functions isolated from external dependencies [[02:24](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=144)].
        
    - _Integration Testing:_ Verifies that separate system modules communicate correctly [[02:35](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=155)].
        
    - _Regression Testing:_ Confirms that new feature logic does not break existing application behavior [[02:40](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=160)].
        

#### 2. Structural Deployment Environments

To keep development safe, tech companies segregate code hosting into separate, isolated virtual spaces [[03:12](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=192)]:

1. **Development Environment (Dev):** An internal sandbox environment accessible strictly to development engineers [[03:25](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=205)].
    
2. **Staging Environment:** A pre-production clone used to run end-to-end user journeys or showcase upcoming feature demos to stakeholders [[03:30](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=210)].
    
3. **Production Environment (Prod):** The live, consumer-facing system hosting real users and transactional client data [[03:25](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=205)].
    

### 👥 Manual Deployment vs. CI/CD Pipeline

|**Architectural Metric**|**Manual Lifecycle Flow (Old Way)**|**Automated CI/CD Engine (DevOps)**|
|---|---|---|
|**Operational Workflow**|Developers manually run compilation tasks and write point tests [[04:21](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=261)].|Automated YAML instructions trigger specific scripts upon changes [[04:53](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=293)].|
|**Error Factor**|Highly error-prone and slow to scale [[04:27](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=267)].|Uniform, programmatic validation eliminates human oversight errors [[09:37](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=577)].|
|**Code Integration**|Large, infrequent merges that cause massive merge blockages [[07:59](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=479)].|Small, frequent code updates integrated seamlessly at every push event [[10:08](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=608)].|
|**System Restore Speed**|Long resolution timelines required to reverse broken production code [[09:00](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=540)].|Instant automated fallbacks trigger clean rollbacks to healthy builds [[09:00](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=540)].|
|**Release Velocity**|Rigid, multi-week release cycles (never deploy code on Fridays) [[08:44](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=524), [09:20](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=560)].|Multiple independent functional production drops completed daily [[10:35](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=635)].|

### 🛠️ Industry Tooling Landscape

- **GitHub Actions:** Launched in 2019. It runs natively alongside repositories inside GitHub, making it highly intuitive for teams using standard Git workflows [[12:12](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=732)].
    
- **Jenkins:** An established, flexible open-source orchestrator launched in 2011. While highly customizable with a massive plugin ecosystem, it requires significant manual infrastructure maintenance [[12:33](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=753), [12:53](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=773)].
    
- _Other Notable Engines:_ CircleCI, GitLab CI/CD, Travis CI, and Bamboo [[11:45](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=705)].
    

### 🚀 Zero-Downtime Deployment Strategies

When launching a brand-new code version (`v4`) to replace the current system (`v3`), DevOps engineers use specialized deployment strategies to prevent app down-time [[15:26](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=926)]:

#### A. Blue-Green Deployment

- The system provisions two completely identical tracking infrastructures [[15:45](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=945)].
    
- **Blue** hosts the active live traffic (`v3`), while **Green** staging tests the incoming version (`v4`) [[15:53](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=953)].
    
- Once validated, the network router instantly switches 100% of incoming traffic over to the Green block [[16:23](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=983)]. If a critical bug slips through, the router switches traffic straight back to Blue, mitigating widespread runtime issues [[16:28](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=988)].
    

#### B. Canary Deployment

- Instead of switching all traffic instantly, the router shifts a tiny slice (e.g., 5% to 10%) of real-world user traffic onto the new code version [[16:45](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=1005)].
    
- The team monitors error metrics from this small group. If the system remains healthy over a multi-hour window, the deployment progressively scales out to 25%, 50%, and eventually 100% of the network [[17:09](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=1029)].
    

#### C. Rolling Deployment

- Commonly coordinated by a Load Balancer spanning multiple active server nodes [[17:34](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=1054)].
    
- The system takes down individual server instances one by one, upgrades them to the new code package, runs health checks, and drops them back into service until the entire cluster is upgraded [[17:54](http://www.youtube.com/watch?v=gLptmcuCx6Q&t=1074)].
    

_Tip: Save this note under your `DevOps/` or `System_Architecture/` folder in Obsidian to maintain an excellent overview of production engineering logic._
