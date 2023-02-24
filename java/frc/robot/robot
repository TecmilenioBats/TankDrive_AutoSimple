// Copyright (c) FIRST and other WPILib contributors.
// Open Source Software; you can modify and/or share it under the terms of
// the WPILib BSD license file in the root directory of this project.

package frc.robot;

import edu.wpi.first.wpilibj.TimedRobot;
import edu.wpi.first.wpilibj.Joystick;
import edu.wpi.first.wpilibj.motorcontrol.Spark;
import com.revrobotics.CANSparkMax;
import com.revrobotics.CANSparkMaxLowLevel.MotorType;
import edu.wpi.first.wpilibj.Timer;

/**
 * The VM is configured to automatically run this class, and to call the functions corresponding to
 * each mode, as described in the TimedRobot documentation. If you change the name of this class or
 * the package after creating this project, you must also update the build.gradle file in the
 * project.
 */
public class Robot extends TimedRobot {
  /**
   * This function is run when the robot is first started up and should be used for any
   * initialization code.
   */

    private CANSparkMax m_leftmotor1 = new CANSparkMax(2, MotorType.kBrushed);
    private CANSparkMax m_rightmotor1 = new CANSparkMax(3, MotorType.kBrushed);
    private Spark m_leftmotor2 = new Spark(0);
    private Spark m_rightmotor2 = new Spark(0);

    private Joystick driverJoystick = new Joystick(0);
    private Joystick operatorJoystic = new Joystick(1);

    private double startTime;

  @Override
  public void robotInit() {}

  @Override
  public void robotPeriodic() {}

  @Override
  public void autonomousInit() {

    startTime = Timer.getFPGATimestamp();

  }

  @Override
  public void autonomousPeriodic() {

    double time = Timer.getFPGATimestamp();

    if (time - startTime < 3){
      m_leftmotor1.set(0.4);
      m_leftmotor2.set(0.4);
      m_rightmotor1.set(0.4);
      m_rightmotor2.set(0.4);
    } else {
      m_leftmotor1.set(0);
      m_leftmotor2.set(0);
      m_rightmotor1.set(0);
      m_rightmotor2.set(0);
    }

  }

  @Override
  public void teleopInit() {}

  @Override
  public void teleopPeriodic() {

    double speed = -driverJoystick.getRawAxis(1) * 0.6;
    double turn = driverJoystick.getRawAxis(2) * 0.3;

    double left = speed + turn;
    double right = turn - speed;

    m_leftmotor1.set(left);
    m_leftmotor2.set(left);
    m_rightmotor1.set(right);
    m_rightmotor2.set(right);

  }

  @Override
  public void disabledInit() {}

  @Override
  public void disabledPeriodic() {}

  @Override
  public void testInit() {}

  @Override
  public void testPeriodic() {}

  @Override
  public void simulationInit() {}

  @Override
  public void simulationPeriodic() {}
}
