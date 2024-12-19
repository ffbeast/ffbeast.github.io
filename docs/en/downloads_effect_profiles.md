---
layout: default
title: Effect profiles
parent: Downloads
nav_order: 2
---

- TOC
{:toc}

---

## Disclaimer

{: .warning }
> As each and every FFBEast base is unique because can be built with different components (motors, controllers) and
> with different mechanical scheme, profiles created on one device can cause high forces, excessive dampening or oscillations on another device. 
> In that case some tuning of effects (usually spring forces and smart dampening) could be needed for your specific FFB base.    

{: .important }
> All profiles there are in JSON format, and often browser treat it as normal document and opens in a new page. Use **"
> Right Click"** and **"Save As"** approach for downloading it.

{: .important }
> Put downloaded JSON file to the _effect_profiles_ folder to be visible by Commander.

# Templates

Generic templates are not bound to some specific game. It's just baseline and mimics "average" behaviour of flight controls.
By removing non relevant effects and/or changing type of a main spring effect it is possible to adjust 
templates to the most modules present in games.

- [**Generic jet template**](../../assets/profiles/GENERIC___Jet_template___mix_of_DirectX_and_relevant_telemetry_shakers.json) **(by FFBeast)**
  - Stick only
  - Includes relevant shakers
  - Includes hardware trim effect
  
<!-- -->

- [**Generic prop airplane template**](../../assets/profiles/GENERIC___Prop_airplane_template___mix_of_DirectX_and_relevant_telemetry_shakers.json) **(by FFBeast)**
  - Stick only
  - Includes relevant shakers
  - Includes hardware trim effect

<!-- -->

- [**DirectX based helos template**](../../assets/profiles/GENERIC___Helos_template___mix_of_DirectX_with_dampening_and_shakers.json) **(by FFBeast)**
  - Stick only
  - Includes relevant shakers
  - Includes hardware trim effect
  - DirectX effect as the main source of force and relies completely on implementation of FFB in game.

<!-- -->

- [**Generic helos template**](../../assets/profiles/GENERIC___Helos_template___mix_of_light_spring_with_dampening_and_shakers.json) **(by FFBeast)**
  - Stick only
  - Includes relevant shakers
  - Includes hardware trim effect
  - This profile uses simple spring as the main source of force and independent from DirectX FFB implementation

# DCS

## F-5E

- [**F-5E**](../../assets/profiles/DCS_F_5E_From_JustFlyIt.json) **(by** [**JustFlyIt**](https://www.youtube.com/@justflyit7569))
  - Stick + Rudder
  - From real pilot as close IRL as possible.
  - No "vanilla" effects and shakers on the stick

<!-- -->

- [**F-5E**](../../assets/profiles/DCS_F_5E_From_FFBeast.json)  **(by FFBeast)**
  - Stick
  - Full set of "vanilla" shakers.
  - Depends on trim set in game. 

## F-14

- [**F-14**](../../assets/profiles/DCS_F_14_From_FFBeast.json) **(by FFBeast)**
  - Stick
  - Full set of "vanilla" shakers.
  - Depends on trim set in game.

## F-16C

- [**F-16C**](../../assets/profiles/DCS_F_16C_From_FFBeast.json) **(by FFBeast)**
  - Stick
  - Full set of "vanilla" shakers.
  
## F/A-18C

- [**F/A-18C**](../../assets/profiles/DCS_FA_18C_From_JustFlyIt.json) **(by** [**JustFlyIt**](https://www.youtube.com/@justflyit7569))
  - Stick + Rudder
  - From real pilot as close IRL as possible.
  - No "vanilla" effects and shakers on the stick

<!-- -->

- [**F/A-18C**](../../assets/profiles/DCS_FA_18C_From_FFBeast.json) **(by FFBeast)**
  - Stick
  - Full set of "vanilla" shakers.

## Mi-8

- [**Mi-8**](../../assets/profiles/DCS_Mi_8_From_JustFlyIt.json) **(by** [**JustFlyIt**](https://www.youtube.com/@justflyit7569))
  - Stick + Rudder
  - From real pilot as close IRL as possible.
  - No "vanilla" effects and shakers on the stick

## MiG-29

- [**MiG-29**](../../assets/profiles/DCS_MiG_29_From_JustFlyIt.json) **(by** [**JustFlyIt**](https://www.youtube.com/@justflyit7569))
  - Stick + Rudder
  - From real pilot as close IRL as possible.
  - No "vanilla" effects and shakers on the stick

## P-47D

- [**P-47D**](../../assets/profiles/DCS_P_47D_From_JustFlyIt.json) **(by** [**JustFlyIt**](https://www.youtube.com/@justflyit7569))
  - Stick + Rudder
  - From real pilot as close IRL as possible.
  - No "vanilla" effects and shakers on the stick

## Spitfire

- [**Spitfire**](../../assets/profiles/DCS_Spitfire_From_JustFlyIt.json) **(by** [**JustFlyIt**](https://www.youtube.com/@justflyit7569))
  - Stick + Rudder
  - From real pilot as close IRL as possible.
  - No "vanilla" effects and shakers on the stick

<!-- -->

- [**Spitfire**](../../assets/profiles/DCS_Spitfire_Based_on_JustFlyIt_profile_with_all_relevant_shakers.json) **(by FFBeast)**
  - Stick + Rudder
  - Based on profile from **JustFlyIt** with addition of relevant shakers for all axes

## Su-27

- [**Su-27**](../../assets/profiles/DCS_Su_27_From_JustFlyIt.json) **(by** [**JustFlyIt**](https://www.youtube.com/@justflyit7569))
  - Stick + Rudder
  - From real pilot as close IRL as possible.
  - No "vanilla" effects and shakers on the stick