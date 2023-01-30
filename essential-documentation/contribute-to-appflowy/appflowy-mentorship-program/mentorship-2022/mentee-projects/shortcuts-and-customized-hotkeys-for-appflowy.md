---
description: Mayur Mahajan
---

# Shortcuts and Customized Hotkeys for AppFlowy

#### Introduction

* Appflowy is now my favorite knowledge management tool and there are many who share my opinion. Appflowy provides many useful features.&#x20;
* But it currently lacks in one area. Although many useful functionalities can be achieved using AppFlowy, there are many widely accepted shortcuts that appflowy currently does not support.&#x20;
* Shortcuts are key combinations that allow users to quickly achieve some functionality. They improve the users' productivity. Using keyboard shortcuts is much faster than using the mouse.&#x20;
* One of the main edges AppFlowy has over its competitors is the ability to have a customizable user experience. Many applications offer users a way to customize keyboard shortcuts to their desired functionality but currently, there is no such mechanism in AppFlowy.

#### Goal

* We need to implement a bunch of functionalities based on some key combinations or single key presses. These shortcuts can be classified into two types:&#x20;
  1. Predefined Shortcuts
  2. Customizable Shortcuts
* Predefined Shortcuts will be a set of commonly used key combinations that help in simple text editing, cursor movement, element selection, etc. These shortcuts will be inspired by other desktop applications, which will give our users a uniform experience across their desktop apps. Thus through this project, our goal is to support many standard shortcuts.
* Customizable Shortcuts is an advanced functionality that will allow users to customize key combinations to achieve their desired functionality with AppFlowy. This feature truly aligns perfectly with the vision of AppFlowy in providing a customizable user experience. Through this project, our goal is to allow users to customize a key combinations.

#### Implementation Design

Let us talk about how the Apps UI might change after we achieve the afore mentioned changes.

<figure><img src="https://lh6.googleusercontent.com/8acgPnXfRtgOEeOCKFoF-zVhunHsHCkZL8ZQhd1QyZYtSPzaXu4mhveVTtZ5u-Gjs_Xd2t_jBMRdko-8SXKaVWD8dIYKTLxQwd897KHaP7CzQWtCBF2KlVweMD9jnUohIUyBO-wYNruzfWSaOB4as9E5rClQKH2yv-znB5M97OlN4mQ2ixk2I0pMndU_rg" alt=""><figcaption><p>Users will see a Shortcuts tab in the settings</p></figcaption></figure>

In the settings, a Shortcuts option will appear which shows all the custom shortcuts

<figure><img src="https://lh4.googleusercontent.com/c31poLrKyi3f0emX_57-EDbL0m1thuJMJLJ0lYrae_9WoN5pUcbY-H_y4H75SLhwMBCq7DtpVQay89mzNm_GTdukK58YZNA3mXyA5BmQ761_lDRqdOMFgW1lGFHMzdwp2stvWedbZRqjgNrXoC5JUgZ6jWBwSgGubzHqy6fG2tup_xfcufAzYjcwW9IIOQ" alt=""><figcaption><p>Predefined shortcuts link</p></figcaption></figure>

In the shortcuts tab users can customize some shortcuts and through a link they can also see a list of predefined shortcuts(this link will open up in a browser).

<figure><img src="https://lh3.googleusercontent.com/BSFBD_ZPa2X4gP7hwCMs2jwxHorr9BiwmtoKaeI5BS4tG4ThHFth2MJI8UJdeRmjhlbDiBaE4HIRW4r8q32dU6TybllCFUf42yqh4jS2kNxtoHflsIn6YyDt5Wj5vY4t5uebTie-DbbwxFaCPBcoa8rNjSdY2uO16i9_m5imdhQmWzm8hV0V0XNEuFsj5g" alt=""><figcaption><p>Add Custom Shortcut option</p></figcaption></figure>

Clicking any existing key combination, will open a popup for assigning new key combination to that functionality. This popup will contain an input field where user can enter the key, they can add more keys and create a unique combination. Users can also change the order of keys occurrence in the shortcut. Finally selecting done will save this key combination to achieve the desired functionality.

