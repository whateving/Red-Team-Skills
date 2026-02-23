# Geolocating Images: Reverse Image Search

## 1. The Core Concept

The very first step in geolocating an image is asking: **"Where does this image appear on the internet?"**
If an image is hosted on a site with geographic context (e.g., `ILoveEgypt.com`), your job is instantly easier. To find out where an image lives online, we rely on **Reverse Image Search** engines.

---

## 2. The Tool Hierarchy (According to OSINT Investigators)

There are many reverse image search tools, but the hierarchy of effectiveness is incredibly stark. If we were to rank them from 1 to 103, it would look like this:

* **#101:** Yandex
* **#102:** Bing
* **#103:** Google

**The Analogy:** Yandex is to Google what a Formula 1 racing car is to a $200 beater car you bought off your friend Ivan (who *swears* it isn't stolen, even though the police have been tailing you all week). 
* **The Golden Rule:** Always use Yandex first. Use it a hundred times before resorting to Bing, and only use Google as an absolute last resort.

---

## 3. How They Work: AI vs. Exact Match

* **Yandex (The Subject Finder):** Yandex utilizes aggressive AI. It doesn't just look for the exact image file; it analyzes the image to understand *what* or *who* it is, and then shows you other images of that exact same subject, instantly building context.
* **Google (The File Finder):** Google's approach is much more rigid. It essentially searches its database for an exact file match. If the exact file hasn't been uploaded and indexed before, Google usually fails to find relevant context.

---

## 4. Further Reading

For a deep dive into the technical differences and investigative methodologies between these engines, refer to Bellingcat's official analysis:
* [Guide to Using Reverse Image Search for Investigations (Bellingcat)](https://www.bellingcat.com/resources/how-tos/2019/12/26/guide-to-using-reverse-image-search-for-investigations/)

<img width="1470" height="298" alt="image" src="https://github.com/user-attachments/assets/9c6ddd32-5e51-49fe-b031-f831a5414286" />


As you can see from the picture above, the reverse image search gives the results for Karamay, which is a prefecture-level city located in the northwestern part of the Xinjiang Uyghur Autonomous Region in China.

# Geolocating Images: Manually 

We are going to look for the name of the place that has likely set up the webcam that allowed us to capture this photo. 

<img width="1008" height="547" alt="image" src="https://github.com/user-attachments/assets/8b02b257-ea50-450b-bf30-063eb5a6b689" />

As you can see in the picture, there is a "Sports Corner" store located on n sheffield ave 1000 w. Searching this on Google Maps and then looking at the building on the opposite side of the road
shows us that the place that had likelly the webcam set up was "Wrigleyville Sports".

<img width="441" height="278" alt="image" src="https://github.com/user-attachments/assets/b2284946-1ea1-4b93-9a02-869b42603598" />

