# PlayFair - ReadMe

### Overview
PlayFair is a robust, developer-friendly system designed to maintain fairness and detect unusual behavior in your games. Developed by **NoSleepKid** from **NukStudios**, PlayFair ensures that your players enjoy a cheat-free gaming experience without any integration of PlayFab—this is a fully original system.

### Features
- **Anti-Cheat Detection**:
  - Detects auto-clickers.
  - Identifies non-human mouse movements.
  - Monitors unnatural keyboard typing patterns.
- **Callback-Driven Architecture**:
  - Customizable callbacks for handling detected cheats.
  - Interfaces for seamless integration into your game logic.
- **Developer-Friendly**:
  - Simple setup with minimal configuration.
  - Expandable and modifiable for personal use.

---

### Getting Started
1. **Import PlayFair into Your Project**:
   - Add the PlayFair script(s) to your project.

2. **Attach the PlayFair Component**:
   - Add the `PlayFair` MonoBehaviour to a GameObject in your scene.
   - Use the `DontDestroyOnLoad` pattern to keep PlayFair persistent.

3. **Implement Interfaces**:
   - To receive callbacks, create a MonoBehaviour that implements one or more PlayFair interfaces:
     - `IOnPlayFairInitCallback`: Notifies when PlayFair initialization is complete.
     - `IPlayFairCheatCallbacks`: Handles cheat detection events.

Example:
```csharp
public class CheatDetectionHandler : MonoBehaviour, IPlayFairCheatCallbacks
{
    public void OnAutoClickerDetected()
    {
        Debug.Log("Auto-clicker detected! Taking action.");
    }

    public void OnNonHuminoidMouseMovementsDetected()
    {
        Debug.Log("Non-human mouse movements detected!");
    }

    public void OnNonHumanoidKeyboardTypingDetected()
    {
        Debug.Log("Unnatural keyboard typing detected!");
    }
}
```

4. **Initialization**:
   - PlayFair automatically finds objects implementing `IOnPlayFairInitCallback` during startup and calls `OnPlayFairInitComplete()`.

---

### Interfaces
#### `IOnPlayFairInitCallback`
- Callback for when PlayFair finishes initializing.
```csharp
void OnPlayFairInitComplete();
```

#### `IPlayFairCheatCallbacks`
- Callbacks for detecting specific cheats.
```csharp
void OnAutoClickerDetected();
void OnNonHuminoidMouseMovementsDetected();
void OnNonHumanoidKeyboardTypingDetected();
```

---

### Notes & Guidelines
- **Modifications**:
  - You are welcome to modify PlayFair for personal use.
  - Please do not sell modified versions or claim ownership.
- **Support**:
  - For help or suggestions, contact us on Discord.
- **Naming Clarification**:
  - "PlayFair" does not reference PlayFab. Any resemblance is purely coincidental.

---

### Legal & License
By using PlayFair, you agree to:
- Not sell this software or modified versions for monetary gain.
- Credit **NukStudios** for the original system.

For further assistance, reach out to **NoSleepKid** at NukStudios.

Happy coding, and keep it fair!

