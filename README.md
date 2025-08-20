<!-- markdownlint-disable MD041 -->
<!-- markdownlint-disable MD033 -->
<!-- markdownlint-disable MD045 -->
<!-- markdownlint-disable MD013 -->

![banner](notes/images/Urban%20Growth%20and%20Rising%20Waters.png)

## __THE CURIOUS MINDS💡!__

*Welcome to the Curious Minds' repository! We are thrilled to have you here.*

Exploring Data Science with Python — Learning Together, Building Trust.

## 🧭 Who are we?

We are a diverse team of aspiring data scientists brought together by a shared
passion for solving real-world problems through data.
Our project explores the relationship between urban growth and flood risk in East
 African cities, where rapid development meets the challenges of climate change.
By combining satellite imagery, rainfall data, and open-source tools, we aim to
uncover patterns that can support smarter urban planning and resilience.
Through this journey, we’re not just learning to code — we’re learning to think
critically, collaborate effectively, and use data for impact.

---

## About Our Project

>You can access more information about the process of choosing the question in the
[`brainstorming.md`](0_domain_study/brainstorming.md) file.

### 🚀 Problem Statement

Urban flooding is becoming increasingly common in rapidly growing cities. As
cities expand, natural land surfaces are replaced with buildings, roads,
and other infrastructure. This change __reduces the land’s ability to
absorb rainfall__, potentially leading to more severe and frequent floods.
Despite these concerns, there is limited data-driven research quantifying the
relationship between urbanization and flood extent in the __East African__ regions.

This is where data science can play a transformative role. By leveraging
satellite imagery, hydrological data, current and historical climate data, such
as flood patterns, together with machine learning models, we can develop early
warning systems, improve flood forecasting, and optimize emergency response
efforts.The goal is __to support better urban planning and disaster risk management
by providing a clearer understanding of how unchecked urban growth may influence
flood risks.__

### 🧠 Our Group's Understanding Of The Problem Domain

*Access our Group's detailed
understanding
of the domain in
the [`background review.md`](0_domain_study/background_review.md) file and
[`Summary of Understanding.md`](0_domain_study/summary_of_our_understanding.md)
file.*

---

## 🔬 Actionable Research Questions

 __*How has urban expansion influenced the frequency and*__
 __*spatial extent of the flood events in Kampala and Addis Ababa, considering*__
  __*rainfall variability?*__

### 🧩 A Non Technical Explanation On How We Chose To Model The Domain?

We wanted to understand how the growth of cities like __Kampala and Addis Ababa__
 might be making floods worse over time, especially when
  combined with changing rainfall patterns. Our goal was to use real satellite
   data to explore whether there's a __connection between urban growth, rainfall,
    and flood events__, and what that might mean for future city planning.
To do this, we looked at three main types of data:

- 🏘️ __Urban Extent__ - *How much of each city is covered by buildings or built-up*
 *land each year*.

- 🌧️ __Rainfall__ – *How much rain fell each month, using high-resolution*
 *satellite rainfall maps*.

- 🌊 __Flood Extent__ – *How much of each city was covered by floodwaters each month*,
 *based on flood mapping from satellite images*.

Since these data sets all come in __different formats and time scales__ (some are
 monthly, others are yearly), we standardized everything to an __annual scale__,
  so we could compare them year by year. These are the
   [`cleaning scripts`](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/tree/main/2_data_preparation/cleaning_scripts)🧹
    we used for the datasets. We combined the three datasets into one big table
     where each row represents a year for a city, with columns for:

- 🌧️ Total rainfall in that year
- 🏙️ Amount of urbanized land
- 🌊 How much flooding occurred

This allowed us to look for patterns like:

1. Do floods get worse in years when urban areas grow fast?

2. Is there more flooding in years with heavier rainfall?

3. Do both factors (rain + buildings) work together to cause floods?

### ⚠️ Possible Flaws In Our Approach

🔁 __Different data time ranges__  

Rainfall and urban extent data go back to 2005 , but flood data only starts
 in 2015.

🏗️ __Urban area does not capture infrastructure quality__  

Urban extent only tells us how much of the land is built-up, but it doesn’t
 tell us if there are proper drainage systems, green spaces, or flood defenses.

📅 __Annual summaries may hide short-term extremes__  

Floods often happen due to intense rainfall in a few days or weeks. Our yearly
 totals may smooth out those spikes.

🌥️ __Flood data is sometimes incomplete__  

Some flood maps from satellites may miss small or fast-dissipating flood events
 due to cloud cover, revisit gaps, or low image quality.

*You can access the datasets used
in the project in the [`datasets`](1_datasets) file.*
> You can see from the visual below how floods are effecting Nile Basin
> communities and causing displacement
---

![flood](notes/images/Location%20of%20flood%20displacement%20events%20in%20Africa%20(2018%20-%202023).jpg)

---

## 🧩 A non-technical explanation of our findings

Due to increased concrete, fewer trees, and faster runoff, it is simple to conclude that floods will worsen as cities grow. The information from Kampala and Addis Ababa, however, presents a more complicated picture.

### Key Findings

1. 🔁 __The Paradox of Simpson: A Statistical Illusion__  

    - The increased urban area appears to be associated with increased flooding when we examined both cities together. However, if examined separately, each city had the opposite pattern: less flooding was frequently associated with development.  

    > 📌 This contradiction is called *Simpson's Paradox*, and it reminds us how important it is to examine cities individually before generalizing.

2. 📈 __Size is not as important as Growth Rate__  

    - According to our data, the entire urban area had a weaker correlation with short-term flood risk than the Urban Growth Rate, which means periods of higher growth rate experienced more short-term floods.

3. 🌧️ __Rainfall Impact__  

    - Rainfall varies yearly but does not show a direct linear relationship with flooding __(a low positive correlation in both__ __cities separately)__. This implies that flooding is influenced by other factors, such as urban infrastructure, topography, and land use — not just rainfall.

4. __Comparative Boxplot findings__  

    - Kampala tends to receive marginally more rainfall on average than Addis Ababa, with both cities showing a similar spread but different extremes.

    - Kampala consistently experiences much larger flood extents, which might reflect differences in topography, urban planning, or drainage systems.

    - Kampala's urban footprint appears substantially larger than Addis Ababa’s, which could influence its flood vulnerability and runoff dynamics.

### How Confident Are We?

✅ Our analyses were statistically significant and revealed consistent patterns separately.

⚠️ However, we recognize limitations:

- 📅 __Annual summaries may hide short-term extremes__  
*Floods often happen due to intense rainfall in a few days or weeks. Our* *yearly totals may smooth out those spikes*.

- Urban data doesn’t account for drainage infrastructure.
- We didn’t include topography or land use detail, both important flood factors.

## 🤷So, Do Cities Make Floods Worse?

__Not always directly__, but when rainfall hits a fast-growing city, the flood risks can __intensify sharply__ unless that growth is matched by smart infrastructure planning.

> For the technical description of our analysis, you can find it in the [data analysis folder](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/tree/main/4_data_analysis).

---

## How do we team up?🤝

We work together in the following ways:

- [`Our Norms`](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/collaboration/README.md)
- [`Our Communication`](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/collaboration/communication.md)
- [`Our Constraints`](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/collaboration/constraints.md)
- [`Our Learning-goals`](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/blob/main/collaboration/learning_goals.md)
- [`Our retrospectives`](https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-01-repo/tree/milestone_0_retrospective/collaboration/retrospectives)

## Meet the amazing minds working on this project👩🏻‍🤝‍👨🏿

- [__Gai Samuel__](https://github.com/GaiSamuel)
- [__Hiba Daffallah__](https://github.com/Hiba-Daffallah)
- [__Rama Arafeh__](https://github.com/RamaBio20)
- [__Nada Hamza__](https://github.com/Nadaali1232)
- [__Dr.Amin Abd Elraheem__](https://github.com/Dr-Amin-K)
- [__Ndubuisi Agbo__](https://github.com/ndubuisia)

### 🤝 Contributing

We welcome contributions! Please see our guidelines
for [`contributing.md`](CONTRIBUTING.md).
