# Red Teaming ML-Based Systems

Machine Learning (ML) systems encounter distinct security challenges compared to traditional IT infrastructure, largely due to their reliance on massive datasets, complex model architectures, and statistical reasoning. 

Because exploiting these advanced systems requires techniques that take longer than standard testing windows, **red team assessments** are typically the preferred method for evaluating ML security.

**Key Assessment Challenges:**
* **Component Interactivity:** ML environments are built from multiple interconnected parts. Security flaws frequently emerge exactly where these components intersect. 
* **Scoping Limitations:** Defining the boundaries of a standard penetration test for an ML system is notoriously difficult.
* **Risk of Blind Spots:** A narrowly scoped test might accidentally skip over vital integration points, allowing critical vulnerabilities to remain completely undetected.

## OWASP Top 10: Attacking ML-Based Systems

Just as OWASP tracks vulnerabilities for web and mobile applications, they also maintain a Top 10 list for Machine Learning security risks. Because ML systems rely heavily on data and complex pipelines, they introduce unique attack vectors.

### The ML OWASP Top 10

* **ML01: Input Manipulation Attack**
    * **Concept:** Altering the data fed into a live model to force an incorrect or malicious prediction. 
    * **Example:** Applying imperceptible modifications (like specially designed stickers or graffiti) to a stop sign, causing an autonomous vehicle's vision system to misclassify it.
* **ML02: Data Poisoning Attack**
    * **Concept:** Injecting deceptive or malicious data into the model's *training* dataset.
    * **Impact:** Degrades overall accuracy or establishes hidden backdoors (e.g., teaching an antivirus classifier that a specific family of malware is "benign").
* **ML03: Model Inversion Attack**
    * **Concept:** Training a secondary model to analyze the target model's *outputs*, with the goal of reverse-engineering and exposing the original *inputs*.
    * **Risk:** Highly dangerous for models trained on sensitive information (like medical records), as it can leak private data.
* **ML04: Membership Inference Attack**
    * **Concept:** Probing a model to determine whether a specific data point was included in its original training set.
    * **Mechanism:** Attackers exploit the fact that models usually process familiar training data with higher confidence and lower error rates than unseen data.
* **ML05: Model Theft (Extraction)**
    * **Concept:** Systematically querying a target model and observing its decision-making process to train a functional replica.
    * **Impact:** Results in the theft of proprietary intellectual property and potentially exposes the underlying logic.
* **ML06: AI Supply Chain Attacks**
    * **Concept:** Targeting the broader, interconnected ecosystem required to build ML systems. This includes exploiting vulnerabilities in third-party datasets, open-source libraries, or external APIs.
* **ML07: Transfer Learning Attack**
    * **Concept:** Compromising a foundational, open-source pre-trained model. 
    * **Impact:** When developers adopt and fine-tune this tainted baseline for their own applications, the embedded biases or backdoors persist into the final system.
* **ML08: Model Skewing**
    * **Concept:** Intentionally injecting biased or incorrectly labeled data to shift the model's decision boundaries in favor of the attacker.
* **ML09: Output Integrity Attack**
    * **Concept:** Intercepting and manipulating the model's *results* before the downstream system can process them.
    * **Evasion:** Because the model itself functions normally and remains completely untouched, traditional model-centric security measures will fail to detect this.
* **ML10: Model Poisoning**
    * **Concept:** Directly modifying the internal architecture, weights, or parameters of the model.
    * **Requirement:** Unlike data poisoning, this requires the attacker to have direct access to the model itself. It is difficult to execute without degrading overall performance, but it allows for highly precise backdoor insertion.
