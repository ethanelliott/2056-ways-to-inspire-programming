![title](http://2056.ca/wp-content/uploads/2015/03/Untitled-2.png)

<center>
  <h1>
  <code><i>Coding for Success</i></code>
</h1>
</center>

# Presentation

Available for download. See above.

# Sample code

Below are some examples of various code elements discussed during the presentation.

## Naming Conventions

```c++
    int intakeState;                  //Variable
    const int INTAKE_OFF = 0;         //Constant
    float kP = 0.01;                  //Member constants
    void setIntakeSpeed(float speed); //Member functions
```

## State Machine

```c++
void intakeStateMachine() {
        switch (intakeState) {
        case INTAKE_OFF:
            SmartDashboard::PutString("Intake", "OFF");
            setIntakeSpeed(0.0);
            break;
        case INTAKE_IN:
            SmartDashboard::PutString("Intake", "IN");
            setIntakeSpeed(0.75);
            break;
        case INTAKE_OUT:
            SmartDashboard::PutString("Intake", "OUT");
            setIntakeSpeed(-1);
            break;
        }
        if (driveGamePad->GetNumberedButton(1)) {
            intakeState = INTAKE_IN;
        } else if (driveGamePad->GetNumberedButton(2)) {
            intakeState = INTAKE_OFF;
        } else if (driveGamePad->GetNumberedButton(3)) {
            intakeState = INTAKE_OFF;
        } else if (driveGamePad->GetNumberedButton(4)) {
            intakeState = INTAKE_OFF;
        } else if (driveGamePad->GetNumberedButton(8)) {
            intakeState = INTAKE_OUT;
        } else {
            intakeState = INTAKE_OFF;
        }
    }
`
```

# References and Other Links

Reference              | Link
---------------------- | -----------------------------------------------
2056 Website           | <http://2056.ca>
Team Manual            | <http://2056.ca/team-manual/>
WPILib                 | <https://wpilib.screenstepslive.com/s/4485>
Team 1114 Code Release | <https://www.chiefdelphi.com/media/papers/3180>
Team 254 Code Release  | <https://github.com/Team254/FRC-2017-Public>
