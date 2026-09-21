# Driving Restriction Input / Output Flowchart

This document details the complete Input, Processing, and Output logic for the AAOS WebView Media Hub's Driving Restriction Overlay mechanism.

## Visual Flowchart Diagram

![AAOS WebView Media Hub - Driving Restriction Input/Output Flowchart](/home/pasap86/.gemini/antigravity/brain/ca683773-78e1-4c8b-96e2-36d7d8b83c3e/driving_restriction_flowchart_1789978926409.jpg)

---

## Mermaid Flowchart Definition

```mermaid
flowchart TD
    %% INPUTS
    subgraph INPUTS ["📥 INPUTS"]
        Url["1. Current Web URL<br/>(e.g., youtube.com)"]
        State["2. Driving State<br/>(Driving / Parked)"]
        Json["3. Active JSON Config<br/>(Allowed App IDs)"]
    end

    %% PROCESSING
    subgraph PROCESS ["⚙️ PROCESSING DECISION TREE"]
        CheckHome{"Is current URL<br/>the Home Hub?"}
        MatchDomain["Match URL domain to App Config<br/>(e.g., youtube.com ➔ ID: youtube)"]
        CheckJson{"Is App ID in<br/>Active JSON List?"}
        SetRestrictedFalse["Set drivingRestriction = FALSE<br/>(Allowed App)"]
        SetRestrictedTrue["Set drivingRestriction = TRUE<br/>(Restricted App)"]
        CheckDriving{"Is Vehicle<br/>in DRIVING mode?"}
    end

    %% OUTPUTS
    subgraph OUTPUT_RESTRICTED ["🚫 OUTPUT: RESTRICTED"]
        ShowOverlay["• Show Dark Overlay Screen (View.VISIBLE)<br/>• Show Native Media Controls (View.VISIBLE)<br/>• Activate MediaSession (Steering Controls)<br/>• Audio plays in background"]
    end

    subgraph OUTPUT_ALLOWED ["🎵 OUTPUT: ALLOWED"]
        HideOverlay["• Hide Overlay (View.GONE)<br/>• Hide Native Control Bar (View.GONE)<br/>• Deactivate MediaSession<br/>• Full interactive Web Video display"]
    end

    %% CONNECTIONS
    Url --> CheckHome
    CheckHome -- "YES (Home Page)" --> HideOverlay
    CheckHome -- "NO (Web App)" --> MatchDomain

    MatchDomain --> CheckJson
    Json -.-> CheckJson

    CheckJson -- "YES (e.g. spotify in Spotify Config)" --> SetRestrictedFalse
    CheckJson -- "NO (e.g. youtube in Spotify Config)" --> SetRestrictedTrue

    SetRestrictedFalse --> CheckDriving
    SetRestrictedTrue --> CheckDriving
    State -.-> CheckDriving

    CheckDriving -- "NO (Parked)" --> HideOverlay
    CheckDriving -- "YES (Driving) & Allowed App" --> HideOverlay
    CheckDriving -- "YES (Driving) & Restricted App" --> ShowOverlay
```

---

## Technical Summary of I/O Data Flow

### 1. Inputs
* **`currentUrl`**: The URL being navigated to inside the WebView.
* **`isDrivingState`**: Boolean flag set by the **Drive / Park Sim button**.
* **`allowedWhileDrivingIds`**: Set of App IDs parsed from the **JSON Config Toggle button** (`1st Config` or `2nd Config`).

### 2. Processing Steps
1. **Home Page Bypass**: If `isHomeUrl(currentUrl)` returns `true`, restriction is bypassed immediately.
2. **Domain Matching**: `AppConfigManager` matches `currentUrl` with the app's `domain` (e.g. `"youtube.com"` maps to `id: "youtube"`).
3. **JSON Lookup**: Checks if `allowedWhileDrivingIds` contains `"youtube"`. If not present, `drivingRestriction` is set to `true`.
4. **State Evaluation**: `isRestrictedApp = isDrivingState && drivingRestriction`.

### 3. Output States
* **Restricted (`isRestrictedApp == true`)**:
  * Dark Overlay Container: `View.VISIBLE`
  * Native Media Controls Bar: `View.VISIBLE`
  * MediaSession Controller: `activate()`
  * Playback: Background audio only
* **Allowed (`isRestrictedApp == false`)**:
  * Dark Overlay Container: `View.GONE`
  * Native Media Controls Bar: `View.GONE`
  * MediaSession Controller: `deactivate()`
  * Playback: Unrestricted video & web UI
