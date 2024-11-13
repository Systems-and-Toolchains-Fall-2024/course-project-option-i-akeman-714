[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/VuODydzp)
# Couse Project Option 1
Jinsong Yuan & Daren Yao

ANDREW ID: jinsongy | darenyao

# CODE WALKTHROUGH

The final course project local code is `course_project_local_final_11_12.ipynb`. For the cloud version of the code, refer to [Cloud Code Version].

## Table of Contents
1. [Overview](#overview)
2. [Task Structure](#task-structure)
3. [Function Descriptions by Task](#function-descriptions-by-task)
    - [Task 1](#task-1)
    - [Task 2](#task-2)
    - [Task 3](#task-3)
    - [Task 4](#task-4)
4. [Environment and System Requirements](#environment-and-system-requirements)
5. [Adjustments for Different Environments](#adjustments-for-different-environments)

---

### Overview
Provide a brief summary of the purpose of your course project, including objectives and key deliverables.

### Task Structure
The code is organized into four main tasks, each performing distinct functions related to the project goals. In the local notebook (`course_project_local_final_11_12.ipynb`), Tasks 1, 2, and 3 are clearly divided by markdown sections, while Task 4 is handled separately.

### Function Descriptions by Task

#### Task 1
- **[Function Name]**: Describe the purpose and operation of this function.
- **[Function Name]**: Further explanations, if necessary.

#### Task 2
- **[Function Name]**: Describe the purpose and operation of this function.
- **[Function Name]**: Further explanations, if necessary.

#### Task 3
- **[Function Name]**: Describe the purpose and operation of this function.
- **[Function Name]**: Further explanations, if necessary.

#### Task 4
- **[Function Name]**: Describe the purpose and operation of this function.
- **[Function Name]**: Further explanations, if necessary.

### Environment and System Requirements
List any dependencies, software versions, or packages needed to run the code. Include any Python package versions, hardware requirements, or special configurations.

### Adjustments for Different Environments
Detail the parts of the code that may need to be modified based on the system or environment in which it is run (e.g., file paths, library installation, or hardware configurations). Explain how users can make these changes.

---





# Dataset Feature Description

This dataset is already cleaned.Features with high nullValue ratio are already dropped. URL columns are also dropped. The nullValues has been imputed. For the detail of **DATA CLEANING**, please refer to ```course_project.ipynb```

Based on my understanding of this dataset, some features in this dataset could be furtherly cleaned or developped based on the need of the ML model, including:
- 'nationality_id/nationality_name'
- 'work_rate'

Two features could be dropped (represented by other columns or just useless), including:
- 'body_type'
- 'real_face'_

Below is a detailed explanation of each feature in the dataset.🐈

---

## Output

- **overall**
  - **Description**: The player's overall value.(Supervised Learning output)
  - **Type**: Integer
    
_Note that 'overall' is the ML output, not a input feature._

---

## Basic Information

- **sofifa_id**
  - **Description**: A unique identifier for each player in the SoFIFA database.
  - **Type**: Integer

- **short_name**
  - **Description**: The player's commonly used name.
  - **Type**: String

- **long_name**
  - **Description**: The player's full registered name.
  - **Type**: String

- **player_positions**
  - **Description**: The primary positions the player is adept at, some includes multiple positions separated by commas.
  - **Type**: String
  - **Note**: Could seperate this column into several columns representing the player's preferred positions by 0/1. But this columns information could be substituted by the column of position rating.

- **overall**
  - **Note: !!!This column isn't a input feature!!!** This column is listed here just to directly reflect the structure and the sequence of the dataframe/SQL database. In the ML process, this column should be dropped. The information of this column is introduced above.

- **potential**
  - **Description**: The player's potential maximum rating, indicating their growth ceiling.
  - **Type**: Integer

- **value_eur**
  - **Description**: The player's estimated market value in euros.
  - **Type**: Float

- **wage_eur**
  - **Description**: The player's weekly wage in euros.
  - **Type**: Float

- **age**
  - **Description**: The player's age.
  - **Type**: Integer

- **dob**
  - **Description**: The player's date of birth.
  - **Type**: Date

- **height_cm**
  - **Description**: The player's height in centimeters.
  - **Type**: Integer

- **weight_kg**
  - **Description**: The player's weight in kilograms.
  - **Type**: Integer

---

## Club Information

The female players have a high ratio of NullValue in this part. Many of the female player's club information were set as:
 
 ```StringType```: Unknown;
 ```IntegerType```: median.


- **club_team_id**
  - **Description**: A unique identifier for the player's current club team.
  - **Type**: Integer

- **club_name**
  - **Description**: The name of the club the player is contracted with.
  - **Type**: String

- **league_name**
  - **Description**: The name of the league in which the player's club competes.
  - **Type**: String

- **league_level**
  - **Description**: The tier of the league; lower numbers indicate higher tiers (e.g., 1 for top division).
  - **Type**: Integer

- **club_position**
  - **Description**: The player's primary position at their club.
  - **Type**: String

- **club_jersey_number**
  - **Description**: The squad number assigned to the player at their club.
  - **Type**: Integer

- **club_joined**
  - **Description**: The date when the player joined their current club.
  - **Type**: Date

- **club_contract_valid_until**
  - **Description**: The year until which the player's contract with the club is valid.
  - **Type**: Integer

---

## National Team Information

- **nationality_id**
  - **Description**: A unique identifier for the player's nationality.
  - **Type**: Integer

- **nationality_name**
  - **Description**: The player's nationality.
  - **Type**: String
  - **Note**: Could be dropped since the nationality_id can fully represent this feature. But it could also be transferred through OneHotEncoder and replace the id. It depends on which one is better for the ML model.

---

## Personal Attributes

- **preferred_foot**
  - **Description**: The player's dominant foot, either 'Left' or 'Right'.
  - **Type**: String

- **weak_foot**
  - **Description**: A rating of the player's ability with their non-dominant foot, usually from 1 to 5.
  - **Type**: Integer

- **skill_moves**
  - **Description**: The player's skill move rating, indicating their ability to perform technical moves, from 1 to 5.
  - **Type**: Integer

- **international_reputation**
  - **Description**: A rating of the player's fame on the international stage, from 1 to 5.
  - **Type**: Integer

- **work_rate**
  - **Description**: The player's work rate in attack and defense, formatted as 'Attacking Work Rate/Defensive Work Rate' (e.g., 'High/Medium').
  - **Type**: String
  - **Note**: May be seperating this feature into two parts would be better.
  - 
- **body_type**
  - **Description**: The player's body type (e.g., 'Lean'(170-), 'Normal'(185),'Unique').
  - **Type**: String
  - **Note**: This one is a little tricky to use. There's a (height) after the body type. I think that this column could be dropped because we could use height_cm and weight_kg (features introduced in the basic information section) to represent the body type. And this is more like a classified result, which isn't stronger than numerical features.

- **real_face**
  - **Description**: Indicates whether the player's face is accurately represented in the game.
  - **Type**: String ('Yes' or 'No')
  - **Note**: Useless feature.

---

## Financial Information

- **release_clause_eur**
  - **Description**: The player's release clause amount in euros.
  - **Type**: Float

---

## Overall Ratings

- **pace**
  - **Description**: The player's speed rating, combining acceleration and sprint speed.
  - **Type**: Integer

- **shooting**
  - **Description**: The player's shooting ability rating.
  - **Type**: Integer

- **passing**
  - **Description**: The player's passing ability rating.
  - **Type**: Integer

- **dribbling**
  - **Description**: The player's dribbling ability rating.
  - **Type**: Integer

- **defending**
  - **Description**: The player's defensive ability rating.
  - **Type**: Integer

- **physic**
  - **Description**: The player's physicality rating.
  - **Type**: Integer

---

## Detailed Attributes

### Attacking Attributes

- **attacking_crossing**
  - **Description**: Ability to deliver accurate crosses.
  - **Type**: Integer

- **attacking_finishing**
  - **Description**: Ability to finish scoring chances.
  - **Type**: Integer

- **attacking_heading_accuracy**
  - **Description**: Accuracy of heading the ball.
  - **Type**: Integer

- **attacking_short_passing**
  - **Description**: Skill in short passing.
  - **Type**: Integer

- **attacking_volleys**
  - **Description**: Ability to strike the ball in mid-air.
  - **Type**: Integer

### Skill Attributes

- **skill_dribbling**
  - **Description**: Proficiency in dribbling.
  - **Type**: Integer

- **skill_curve**
  - **Description**: Ability to bend the ball.
  - **Type**: Integer

- **skill_fk_accuracy**
  - **Description**: Accuracy in taking free kicks.
  - **Type**: Integer

- **skill_long_passing**
  - **Description**: Ability to execute long passes.
  - **Type**: Integer

- **skill_ball_control**
  - **Description**: Skill in controlling the ball.
  - **Type**: Integer

### Movement Attributes

- **movement_acceleration**
  - **Description**: How quickly the player reaches top speed.
  - **Type**: Integer

- **movement_sprint_speed**
  - **Description**: The player's top sprint speed.
  - **Type**: Integer

- **movement_agility**
  - **Description**: Ability to change direction quickly.
  - **Type**: Integer

- **movement_reactions**
  - **Description**: The player's reaction time.
  - **Type**: Integer

- **movement_balance**
  - **Description**: Ability to maintain balance.
  - **Type**: Integer

### Power Attributes

- **power_shot_power**
  - **Description**: The power behind shots.
  - **Type**: Integer

- **power_jumping**
  - **Description**: The player's jumping ability.
  - **Type**: Integer

- **power_stamina**
  - **Description**: The player's stamina.
  - **Type**: Integer

- **power_strength**
  - **Description**: Physical strength.
  - **Type**: Integer

- **power_long_shots**
  - **Description**: Ability to score from long-range shots.
  - **Type**: Integer

### Mentality Attributes

- **mentality_aggression**
  - **Description**: Level of aggression.
  - **Type**: Integer

- **mentality_interceptions**
  - **Description**: Ability to intercept passes.
  - **Type**: Integer

- **mentality_positioning**
  - **Description**: Offensive positioning intelligence.
  - **Type**: Integer

- **mentality_vision**
  - **Description**: Ability to see and execute key passes.
  - **Type**: Integer

- **mentality_penalties**
  - **Description**: Penalty-taking ability.
  - **Type**: Integer

- **mentality_composure**
  - **Description**: Ability to remain calm under pressure.
  - **Type**: Integer

### Defending Attributes

- **defending_marking_awareness**
  - **Description**: Defensive awareness and marking ability.
  - **Type**: Integer

- **defending_standing_tackle**
  - **Description**: Ability to perform standing tackles.
  - **Type**: Integer

- **defending_sliding_tackle**
  - **Description**: Ability to perform sliding tackles.
  - **Type**: Integer

### Goalkeeping Attributes

- **goalkeeping_diving**
  - **Description**: Diving ability for goalkeepers.
  - **Type**: Integer

- **goalkeeping_handling**
  - **Description**: Handling ability for goalkeepers.
  - **Type**: Integer

- **goalkeeping_kicking**
  - **Description**: Kicking ability for goalkeepers.
  - **Type**: Integer

- **goalkeeping_positioning**
  - **Description**: Positioning ability for goalkeepers.
  - **Type**: Integer

- **goalkeeping_reflexes**
  - **Description**: Reflexes for goalkeepers.
  - **Type**: Integer

---

## Position Ratings

These attributes indicate the player's effectiveness in specific positions. Higher ratings suggest better suitability.
**The highes score among a players' position rating is similar to the overall value. (Only based on my observation)**
_The rating used to have a format of N+m, N-m or N, I transferred them to a single integer by calculating the result._

- **ls**: Left Striker
- **st**: Striker
- **rs**: Right Striker
- **lw**: Left Winger
- **lf**: Left Forward
- **cf**: Centre Forward
- **rf**: Right Forward
- **rw**: Right Winger
- **lam**: Left Attacking Midfielder
- **cam**: Central Attacking Midfielder
- **ram**: Right Attacking Midfielder
- **lm**: Left Midfielder
- **lcm**: Left Central Midfielder
- **cm**: Central Midfielder
- **rcm**: Right Central Midfielder
- **rm**: Right Midfielder
- **lwb**: Left Wing Back
- **ldm**: Left Defensive Midfielder
- **cdm**: Central Defensive Midfielder
- **rdm**: Right Defensive Midfielder
- **rwb**: Right Wing Back
- **lb**: Left Back
- **lcb**: Left Centre Back
- **cb**: Centre Back
- **rcb**: Right Centre Back
- **rb**: Right Back
- **gk**: Goalkeeper

---

## Other Information

- **year**
  - **Description**: The edition year of the FIFA game corresponding to the data.
  - **Type**: Integer

- **gender**
  - **Description**: The player's gender ('Male':1 or 'Female':0).
  - **Type**: Integer

That's all of the features.🔚

---

# PostgreSQL or NoSQL?

Given that the dataset is highly structured, with comprehensive and consistent rows and columns, using a relational database like PostgreSQL offers significant advantages over a NoSQL database. PostgreSQL is designed to handle structured data efficiently, providing strict schema enforcement, data integrity, and consistency through features like ACID transactions and data constraints. It ensures that the data adheres to a predefined schema, preventing invalid data entries. In contrast, NoSQL databases are better suited for unstructured or semi-structured data, lacking strict schema enforcement, which can lead to data inconsistency in highly structured datasets like this one. In summary, for datasets with a fixed schema, PostgreSQL provides a more appropriate and reliable solution compared to NoSQL databases.
