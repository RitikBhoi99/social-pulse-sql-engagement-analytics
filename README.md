# 📊 Social Pulse — SQL Engagement Analytics

> **Turning social media data into actionable business insights using SQL**

Social Pulse is a SQL-based data analytics project built around a simulated Instagram-style social media platform.

The project analyzes user activity, posts, likes, comments, follows, hashtags, and photo tags to identify engagement patterns and translate them into actionable product, marketing, and user-retention strategies.

---

## 🚀 Project Overview

The dataset contains:

* **100 users**
* **257 posts**
* **7,488 comments**
* **8,782 likes**
* **7,623 follows**
* **21 hashtags**
* **501 photo-tags**
* **7 relational tables**

The analysis follows a simple business framework:

**SQL Analysis → Business Insight → Action**

The project answers **13 objective questions and 10 subjective business questions** using SQL techniques including:

* JOINs
* LEFT JOINs
* GROUP BY
* HAVING
* COUNT / COUNT DISTINCT
* CASE statements
* Window Functions
* RANK()
* CTEs
* Self-JOINs
* Aggregations
* NULL handling
* Data-quality checks

---

## 🎯 Business Objectives

The project focuses on four major areas:

### 1. Data Quality

* Identify duplicate records
* Check missing/NULL values
* Validate relational data
* Recommend constraints for data integrity

### 2. User Engagement

* Analyze posting behavior
* Identify highly active users
* Find inactive users
* Calculate engagement per post
* Rank users by total engagement

### 3. Content & Hashtag Analysis

* Calculate average tags per post
* Identify high-performing hashtags
* Analyze content engagement
* Explore user-generated content for advertising

### 4. Marketing & Growth

* Identify valuable creators
* Find potential influencers
* Segment users by activity
* Design re-engagement strategies
* Identify potential brand ambassadors
* Develop personalized advertising strategies

---

## 🗄️ Database Structure

The project uses seven relational tables:

```text
users
   │
   ├── photos
   │      │
   │      ├── likes
   │      ├── comments
   │      └── photo_tags
   │                  │
   │                  └── tags
   │
   └── follows
```

### Tables

| Table        | Purpose                                 |
| ------------ | --------------------------------------- |
| `users`      | User information                        |
| `photos`     | User-created posts                      |
| `likes`      | Likes received on posts                 |
| `comments`   | Comments on posts                       |
| `follows`    | User follow relationships               |
| `tags`       | Available hashtags                      |
| `photo_tags` | Relationship between posts and hashtags |

---

## 🔍 Key SQL Analysis

### Data Quality Audit

A combined audit was performed across all seven tables to identify duplicate combinations and NULL values.

The analysis showed that the dataset passed the duplicate/NULL checks used in the project.

**Recommendation:** Use appropriate `PRIMARY KEY` and `UNIQUE` constraints to prevent future duplicate records.

---

### 👥 User Activity Analysis

Users were analyzed using:

* Number of posts
* Likes
* Comments
* Overall activity

`LEFT JOIN` was used so that users with no activity were not excluded.

This enabled the creation of user activity segments such as:

* Highly Active
* Moderately Active
* Low Activity

---

### ❤️ Engagement Leaders

Users were ranked using total engagement:

```text
Total Engagement = Likes + Comments
```

The top engagement users included:

| Rank | User        | Engagement |
| ---: | ----------- | ---------: |
|    1 | Eveline95   |        405 |
|    2 | Cesar93     |        385 |
|    3 | Clint27     |        375 |
|    4 | Delfina_V68 |        347 |
|    5 | Aurelie71   |        318 |

These users represent potential high-value creators for loyalty programs, creator campaigns, and exclusive features.

---

### 🏷️ Hashtag Analysis

Hashtags were analyzed based on engagement received by posts using them.

The highest-performing hashtags included:

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

`#dreamy` achieved the highest average likes in the analysis at approximately **35.75 likes per post**.

---

### 📈 Engagement Per Post

Instead of only looking at total engagement, the project also measures:

```text
Average Engagement Per Post
=
(Likes + Comments) / Total Posts
```

This helps identify creators whose individual posts perform strongly even when they do not publish frequently.

---

### 🔁 Reciprocal Follows

A self-join on the `follows` table was used to identify users who eventually followed each other.

The analysis compares:

```text
First Follow Date
        ↓
Follow Back Date
```

This provides a way to study relationship-building and community health.

---

## 👤 User Segmentation

Users can be segmented based on their combined activity:

### 🔥 Highly Active

Frequent posting and high interaction.

**Strategy:**

* Loyalty rewards
* Exclusive features
* Creator programs
* Early access

### 🟡 Moderately Active

Regular activity but lower engagement.

**Strategy:**

* Personalized recommendations
* Engagement campaigns
* Relevant content

### 🔵 Low Activity

Limited posting and interaction.

**Strategy:**

* Welcome-back campaigns
* Notifications
* Contests
* Posting incentives

---

## 📢 Marketing Insights

The analysis demonstrates how social media data can support marketing decisions.

### Influencer Marketing

Potential influencers should be selected using both:

```text
High Followers + High Engagement
```

rather than follower count alone.

### Personalized Advertising

User-generated content can be used to identify:

* Interests
* Trending topics
* Hashtag preferences
* Product/brand interests
* Content themes

These signals can be used to build more relevant audience segments.

---

## ⚠️ Dataset Limitations

The current dataset contains posts through the `photos` table but does **not** distinguish between:

* Photos
* Videos
* Reels

Therefore, the project cannot reliably compare engagement across those content formats.

The dataset also does not contain a dedicated shares field, so engagement rankings use:

```text
Likes + Comments
```

instead of including shares.

Monthly engagement analysis would also require an appropriate date field/filter.

---

## 🧠 Key Business Recommendations

Based on the analysis:

1. **Reward high-value creators** with badges, early access, and loyalty benefits.
2. **Re-engage inactive users** using personalized campaigns.
3. **Use high-performing hashtags** to improve content discovery.
4. **Separate follower reach from engagement** when selecting influencers.
5. **Use user-generated content** for personalized advertising.
6. **Segment users** based on activity and engagement.
7. **Track reciprocal follows** as a community-health signal.
8. **Expand the schema** to support video/reel analytics.
9. **Add campaign data** to measure CTR and conversion rate.
10. **Build recurring engagement leaderboards** when sufficient date data is available.

---

## 🛠️ Tools & Technologies

* **MySQL**
* **SQL**
* Relational Database Analysis
* Data Cleaning
* Exploratory Data Analysis
* Business Analytics
* Data Storytelling

---

## 📂 Project Structure

```text
sql/
    SQL analysis queries

report/
    Detailed project report

presentation/
    Social Pulse storytelling presentation

screenshots/
    Key analysis outputs
```

---

## 📊 Presentation

The project includes a **15-chapter data storytelling presentation** covering:

1. Data Quality
2. User Activity
3. Hashtag Usage
4. Engagement Leaders
5. Followers vs Following
6. Engagement Per Post
7. Inactive Users
8. Personalized Advertising
9. Content Analysis
10. User Engagement Summary
11. Engagement Leaderboard
12. Hashtag Performance
13. Reciprocal Follows
14. User Segmentation
15. Future Opportunities

---

## 👨‍💻 Author

**Ritik Bhoi**

SQL | Data Analytics | Business Intelligence

---

## ⭐ Project Goal

The goal of Social Pulse is not only to write SQL queries, but to demonstrate how SQL analysis can be transformed into **business decisions and actionable recommendations**.

**Raw Data → SQL → Insight → Business Action**
