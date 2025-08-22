# 🕸️ Web Structure Analysis of The Hindu News Portal

This project analyzes the **internal web structure** of the news portal [The Hindu](https://www.thehindu.com) using web crawling and network analysis techniques. The analysis involves crawling internal and external links, filtering nofollow links, visualizing the link network, and running graph metrics to uncover insights about the website's structure.

---

## 📌 Objective

To apply web crawling and network science concepts to map and analyze the internal hyperlink structure of `www.thehindu.com`, and extract key metrics such as centrality, PageRank, and community structure (modularity).

---

## 🧰 Tools & Technologies

- **Screaming Frog SEO Spider** – for web crawling and data extraction  
- **Gephi** – for graph construction, analysis, and visualization  
- **Excel / Google Sheets / Python (optional)** – for filtering and preprocessing the edge list  

---

## 🧩 Methodology

### 1. **Web Crawling**
- Crawled `https://www.thehindu.com` using Screaming Frog.
- Extracted all internal and external URLs.
- Exported outlinks via:


### 2. **Data Preprocessing**
- Removed all links with the `rel="nofollow"` attribute.
- Filtered edge list to keep only:
- `Source`
- `Destination`
- Saved the filtered data as a **directed edge list** for network import.

### 3. **Graph Construction & Analysis**
- Imported edge list into **Gephi**.
- Enabled:
- **Self-loops**
- **Edge merging (Sum strategy)** to combine multiple links between nodes.
- Filtered the graph to:
- Retain only the **giant (largest) connected component**
- Exclude isolated nodes with no inlinks/outlinks

### 4. **Metrics Computed**
- **In-Degree**
- **Out-Degree**
- **Betweenness Centrality**
- **Closeness Centrality**
- **PageRank**
- **Modularity (Community Detection)**

### 5. **Visualization**
- Applied **ForceAtlas 2** layout in Gephi.
- Colored nodes by **modularity class** (clusters).
- Resized nodes by **PageRank**.
- Tuned parameters for clarity and aesthetics (min/max node size, ForceAtlas tuning).

---

## 📊 Results

- Identified **_n_ modularity clusters** (representing logical sections of the site).
- Network visualized with color-coded clusters and node sizes indicating importance.
- Exported the final network graph (included in `visualizations/` folder).

---

## ⚠️ Challenges Faced & Solutions

| Challenge | Solution |
|----------|----------|
| Crawling blocked for some URLs | Adjusted crawl depth and respected `robots.txt` |
| Duplicate edges between nodes | Used 'Sum' merge strategy in Gephi |
| Too many isolated nodes | Filtered graph to largest connected component |
| Overlapping clusters in layout | Tuned ForceAtlas 2 settings and resolution parameter in modularity detection |

> Detailed descriptions of each challenge and resolution are provided in the project report (`report.pdf`).

---

## 📚 References

- The Hindu News Portal: [https://www.thehindu.com](https://www.thehindu.com)  
- Gephi Documentation: [https://gephi.org/users/](https://gephi.org/users/)  
- Screaming Frog: [https://www.screamingfrog.co.uk/seo-spider/](https://www.screamingfrog.co.uk/seo-spider/)  

---

## 📌 License

This project is for academic purposes only. Please do not use it for commercial applications without permission.

---

## ✍️ Author

*Sourit Saha*  and *Harsh Garg*
Course Project – *Social Media Analytics MBA749*  
*IIT Kanpur*

