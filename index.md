---
layout: home
title: "Beyond Open Looks"
author: Keanu Ventura
permalink: /
background: /img/header.jpg
---

# What Makes an NBA Shooter Elite?

We often hear certain players get labeled as elite shooters — but what does that actually mean? Is it their ability to put up high-scoring games? Or their ability
to score consistently while being efficient? Maybe it's the types of shots they put up - wide open catch and shoot looks versus step back threes with a hand in their face. As fans of the game, we celebrate the KD's, the Stephs, the Klays of the league; however, what really separates them from your average NBA shooter? Is it something we can actually measure, or is there more to it than the numbers can tell us?

Which leads me to explore the following question:

#### Are prolific scorers like Kevin Durant, Stephen Curry, and Klay Thompson elite shooters because they get great looks, or because they consistently make tough shots and outperform shot quality metrics?

To get closer to an answer, I’m going to examine mostly per-game shooting metrics from this past season (2024–25), but also per-game shooting metrics from previous seasons for a range of players we typically label as elite, average, or below-average shooters. I’ve already selected Kevin Durant, Stephen Curry, and Klay Thompson as the elite tier. Tobias Harris and Jordan Poole represent middle-of-the-pack scorers, while Josh Giddey and Kyle Kuzma are often considered as players with poor shooting abilities.

I will be analyzing the following per-game metrics:

- Proportion of unassisted points (%UAST_Pts) – how often players score off of shots they created themselves.
- True Shooting Percentage (TS%) – a scoring efficiency measure that accounts for free throws.
- Effective Field Goal Percentage (eFG%) – similar to regular FG%, but gives more weight to three-pointers.
- Shot Quality – this one’s a bit more complex, but arguably the most important.

#### What is Shot Quality?

In essence, Shot Quality is a measure of how good a shot was. It provides an estimate of the likelihood of a shot going in, based on a range of contextual and environmental conditions. Factors such as the distance of the shot, the proximity of the defender, the amount of time on the shot clock, etc. It's easier to look at shot quality as a representation of the expected eFG%. It's important to note that shot quality does not consider the outcome of the shot but focuses purely on the process. By analyzing shot quality and viewing it as a player's expected eFG%, we can compare it with a player's actual eFG% to determine whether or not they are outperforming the quality of looks they get. Essentially, we can determine whether a player is making tougher shots than expected or simply benefiting from great opportunities. To better understand what shot quality captures and ignores, I've broken it down below.

#### Factors that Contribute to Shot Quality:

- Shot Distance – Closer shots tend to be higher quality.
- Shot Angle / Location – Straightaway vs. corner; paint vs. perimeter.
- Shot Type – Layups, dunks, floaters, catch-and-shoot threes, etc.
- Defender Proximity – Tightly contested shots lower quality.
- Time on Shot Clock – Rushed, late-clock attempts are lower quality.
- Time Context – Time since possession started, time remaining, and period.
- Score Differential – Game situation can impact shot value.
- Assisted vs. Unassisted – Assisted shots often lead to more open looks.
- Possession Type – e.g., transition, offensive rebound, turnover, etc.
- Shot Context – Whether it was a putback or a secondary opportunity.
- Game Type – Regular season vs. playoffs.

#### What's NOT Taken Into Account:

- Shooter identity or reputation - Shot Quality is blind to who takes the shot.
- Whether the shot went in – Only the shot's characteristics matter, not the outcome.

### Cleaned Dataframe: Advanced Shooting Metrics per Game by Season for Selected Players

Now that I have introduced the advanced shooting metrics and defined the Shot Quality metric, I prepared the data I analyzed by creating a dataframe. I collected the data from [pbp_stats](https://www.pbpstats.com/) and cleaned it to include only the stats I needed. Each row represents a player in a given season while the columns hold per-game stats that can be used to better understand the players scoring abilities:

- Player – the name of the player.
- Season – the NBA season the stats correspond to.
- Games_Played – number of games played that season.
- Points – average points scored per game.
- Shot_Quality – expected eFG% based on the context of each shot.
- eFG% – effective field goal percentage, accounting for the added value of three-pointers.
- TS% – true shooting percentage, including free throws for a more complete measure of scoring efficiency.
- Usage – proportion of team plays used by the player while on the floor.
- UAST2 – unassisted two-point shots per game.
- UAST3 – unassisted three-point shots per game.
- Gap – the difference between actual eFG% and expected eFG% (Shot_Quality).
- UAST_Total_Pts – total points scored unassisted per game.
- %UAST_Pts – proportion of a player’s points per game that are unassisted.

A preview of the cleaned dataframe is shown below, giving a snapshot of the players and stats included in the analysis.

<div style="width: 100vw; position: relative; left: 50%; margin-left: -50vw; padding: 2rem 0; box-sizing: border-box;">
  <img 
    src="{{ site.baseurl }}/img/cleaned_preview.jpg" 
    alt="Cleaned Data Preview" 
    style="display: block; margin: 0 auto; max-width: 1100px; width: 100%; height: auto; border: 1px solid #ccc; border-radius: 8px;"
  >
</div>

### 2024-25 Season: Shot Quality vs Actual eFG% and Gap for Selected Players 

<div style="width: 100vw; position: relative; left: 50%; margin-left: -50vw; padding: 2rem 0; box-sizing: border-box;">
  <iframe
    src="{{ site.baseurl }}/img/all_players_bar.html"
    style="display: block; margin: 0 auto; max-width: 1000px; width: 100%; height: 700px; border: none;"
    title="Interactive Shot Quality Plot">
  </iframe>
</div>

<div style="width: 100vw; position: relative; left: 50%; margin-left: -50vw; padding: 2rem 0; box-sizing: border-box;">
  <iframe
    src="{{ site.baseurl }}/img/all_players_scatter.html"
    style="display: block; margin: 0 auto; max-width: 1000px; width: 100%; height: 700px; border: none;"
    title="Interactive Shot Quality Plot">
  </iframe>
</div>

### Klay Thompson: Shot Quality vs Actual eFG% and Gap Over the Last 5 Seasons Played

<div style="width: 100vw; position: relative; left: 50%; margin-left: -50vw; padding: 2rem 0; box-sizing: border-box;">
  <iframe
    src="{{ site.baseurl }}/img/klay_season_bar.html"
    style="display: block; margin: 0 auto; max-width: 1100px; width: 100%; height: 600px; border: none;"
    title="Klay Thompson Shot Quality by Season"
    scrolling="auto"
  ></iframe>
</div>


### 2024-25 Season: Self Created Shots vs TS% for Selected Players

<div style="width: 100vw; position: relative; left: 50%; margin-left: -50vw; padding: 2rem 0; box-sizing: border-box;">
  <iframe
    src="{{ site.baseurl }}/img/self_created_scatter.html"
    style="display: block; margin: 0 auto; max-width: 1000px; width: 100%; height: 700px; border: none;"
    title="Interactive Shot Quality Plot">
  </iframe>
</div>


### Kevin Durant vs Kuzma: Shooting Metrics Radar for 2024-25 Season

<div style="position: relative; width: 100vw; left: 60%; right: 50%; margin-left: -50vw; padding: 2rem 0; box-sizing: border-box; background: transparent; overflow: hidden;">
  <div style="max-width: 1000px; margin: 0 auto;">
    <iframe
      src="{{ site.baseurl }}/img/durant_kuzma_radar.html"
      style="display: block; width: 100%; height: 750px; border: none;"
      title="Interactive Shot Quality Plot">
    </iframe>
  </div>
</div>

### 2024-25 Season: Shooting Metrics Durant vs Curry vs NBA League Average

<div style="position: relative; width: 100vw; left: 70%; right: 50%; margin-left: -50vw; padding: 2rem 0; box-sizing: border-box; background: transparent;">
  <div style="max-width: 1100px; margin: 0 auto;">
    <iframe
      src="{{ site.baseurl }}/img/durant_curry_league_bar.html"
      style="display: block; width: 100%; height: 750px; border: none;"
      title="Durant vs Curry vs League Averages">
    </iframe>
  </div>
</div>

### Shot Difficulty in Motion: Visualize Shooters Outperforming Shot Quality Metrics

<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; margin: 2rem 0;">
  <iframe 
    src="https://www.youtube.com/embed/YeFOnKEX8hU" 
    frameborder="0" 
    allowfullscreen 
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;">
  </iframe>
</div>
