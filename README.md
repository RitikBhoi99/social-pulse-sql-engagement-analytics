# 📊 Social Pulse — SQL Engagement Analytics

> **Turning social media data into actionable business insights using SQL.**

## 🚀 Project Overview

**Social Pulse** is a SQL-based data analytics project built around a simulated Instagram-style social media platform.

The project analyzes users, posts, likes, comments, follows, hashtags, and photo tags to identify engagement patterns and translate them into actionable **product, marketing, retention, and content strategies**.

### 📌 Dataset

| Metric         | Value |
| -------------- | ----: |
| 👥 Users       |   100 |
| 📸 Posts       |   257 |
| 💬 Comments    | 7,488 |
| ❤️ Likes       | 8,782 |
| 👥 Follows     | 7,623 |
| #️⃣ Hashtags   |    21 |
| 🏷️ Photo Tags |   501 |
| 🗃️ Tables     |     7 |

**Analysis Framework:**

```text
SQL Analysis → Business Insight → Action
```

---

## 🎯 Objectives

* Audit the database for duplicates and missing values
* Analyze user activity and engagement
* Identify high-value creators
* Calculate engagement per post
* Analyze followers and following behavior
* Identify inactive users
* Analyze hashtag performance
* Identify potential influencers and brand ambassadors
* Segment users based on activity
* Develop marketing and retention recommendations

---

## 🗄️ Database Structure

The project uses 7 relational tables:

```text
users
photos
comments
likes
follows
tags
photo_tags
```

### Relationships

```text
users
 ├── photos
 │    ├── likes
 │    ├── comments
 │    └── photo_tags ─── tags
 │
 └── follows
```

---

## 🛠️ SQL Concepts Used

This project demonstrates:

* `JOIN`
* `LEFT JOIN`
* `SELF JOIN`
* `GROUP BY`
* `HAVING`
* `COUNT()`
* `COUNT(DISTINCT)`
* `SUM()`
* `AVG()`
* `ROUND()`
* `CASE`
* `RANK() OVER`
* `CTE`
* NULL handling
* Data-quality validation

---

## ❤️ Engagement Leaders

Users were ranked based on:

```text
Total Engagement = Likes + Comments
```

Top users included:

| Rank | User        | Total Engagement |
| ---: | ----------- | ---------------: |
|    1 | Eveline95   |              405 |
|    2 | Cesar93     |              385 |
|    3 | Clint27     |              375 |
|    4 | Delfina_V68 |              347 |
|    5 | Aurelie71   |              318 |

These users represent potential high-value creators for loyalty programs, exclusive features, and creator campaigns.

---

## 🏷️ Hashtag Analysis

The project analyzed hashtags based on the engagement received by posts using them.

Top hashtags included:

* `#dreamy`
* `#beauty`
* `#stunning`
* `#delicious`
* `#foodie`
* `#happy`
* `#hair`
* `#photography`
* `#beach`
* `#style`

`#dreamy` had the highest average likes at approximately **35.75 likes per post**.

---

## 📈 Engagement Per Post

The project also measures engagement quality rather than only total engagement.

```text
Average Engagement Per Post
=
(Likes + Comments) / Total Posts
```

This helps identify creators whose individual posts perform strongly even when they publish less frequently.

---

## 👥 User Segmentation

Users can be divided into three activity groups.

### 🔥 Highly Active

Frequent posting and high interaction.

**Strategy:**

* Loyalty rewards
* Exclusive features
* Creator programs
* Early access

### 🟡 Moderately Active

Regular activity with moderate engagement.

**Strategy:**

* Personalized content
* Engagement campaigns
* Relevant recommendations

### 🔵 Low Activity

Limited posting and interaction.

**Strategy:**

* Welcome-back offers
* Notifications
* Contests
* Posting incentives

---

## 📢 Marketing Insights

### Influencer Marketing

The project recommends selecting influencers using:

```text
High Followers + High Engagement
```

rather than relying only on follower count.

### Personalized Advertising

User-generated content can provide signals about:

* Interests
* Popular topics
* Hashtag preferences
* Products
* Brands
* Content themes

These signals can be used to create more relevant audience segments and advertising campaigns.

---

## 🔁 Reciprocal Follows

A self-join was used on the `follows` table to identify users who eventually followed each other.

The analysis compares the first follow with the later follow-back to understand reciprocal relationships and community behavior.

---

## 🧹 Data Quality

The project performed a data-quality audit across all seven tables.

The analysis checked:

* Duplicate records
* Missing / `NULL` values
* Unique records
* Key relationships

The analysis found no identified duplicate records or missing values for the checked fields.

**Recommendation:** Use appropriate `PRIMARY KEY` and `UNIQUE` constraints to maintain data integrity as the platform grows.

---

## ⚠️ Dataset Limitations

The dataset has some limitations:

* The current schema does not distinguish between **photos, videos, and reels**.
* There is no **shares** field, so engagement rankings use likes + comments.
* Monthly engagement analysis requires an appropriate date field/filter.
* Some subjective questions are therefore addressed using the fields actually available in the dataset.

---

## 💡 Business Recommendations

1. Reward highly engaged creators with badges and exclusive benefits.
2. Create personalized re-engagement campaigns for inactive users.
3. Use high-performing hashtags to improve content discovery.
4. Select influencers using both reach and engagement.
5. Use user-generated content for personalized advertising.
6. Segment users based on their activity level.
7. Track reciprocal follows as a community-health signal.
8. Extend the database to support video and reel analytics.
9. Add campaign data to measure CTR and conversion rates.
10. Build recurring engagement leaderboards when sufficient date data is available.

---

## 📂 Project Structure

```text
social-pulse-sql-engagement-analytics/
│
├── README.md
│
├── screenshots/
│   └── social-pulse-slide-1.png
│
├── sql/
│   ├── 01_data_quality.sql
│   ├── 02_user_activity.sql
│   ├── 03_tags_per_post.sql
│   ├── 04_top_engagement_users.sql
│   ├── 05_followers_following.sql
│   ├── 06_avg_engagement_per_post.sql
│   ├── 07_never_liked_users.sql
│   ├── 08_hashtag_ad_targeting.sql
│   ├── 09_content_type_analysis.sql
│   ├── 10_user_engagement_summary.sql
│   ├── 11_engagement_leaderboard.sql
│   ├── 12_top_hashtags.sql
│   ├── 13_reciprocal_follows.sql
│   └── 14_user_segmentation.sql
│
├── report/
│   └── Social_Pulse_SQL_Report.docx
│
└── presentation/
    └── Social_Pulse_Storytelling.pptx
```

---

## 📊 Project Presentation

The project includes a **15-chapter data storytelling presentation** covering:

* Data Quality
* User Activity
* Hashtag Usage
* Engagement Leaders
* Followers vs Following
* Engagement Per Post
* Inactive Users
* Personalized Advertising
* Content Analysis
* Engagement Summary
* Engagement Leaderboard
* Hashtag Performance
* Reciprocal Follows
* User Segmentation
* Future Opportunities

---

## 👨‍💻 Author

### Ritik Bhoi

**SQL | Data Analytics | Business Intelligence**

---

## ⭐ Project Goal

The goal of **Social Pulse** is to demonstrate how SQL can transform raw relational data into meaningful business insights.

```text
Raw Data
   ↓
SQL Analysis
   ↓
Insights
   ↓
Business Recommendations
   ↓
Better Product & Marketing Decisions
```

---

### 🧰 Tools & Technologies

**MySQL · SQL · Data Analytics · Business Analytics · Data Storytelling**
