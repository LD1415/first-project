# first-project

package org.firststinspires.ftc.clawandwheelcontroller;

import com.qualcomm.robptecore.eventloop.opmode.OpMode;
import com.qualcomm.robotecore.eventloop.opmode.TeleOp;

import com.qualcomm.robotcore.hardwere.Servo;
import com.qualcomm.robotcore.hardwere.DcMotor;


@TeleOp(name="exOpMode", group="TeleOp")
public class exOpMode extende OpMode 
  { DcMotor rightMotor;
    DcMotor leftMotor;
    
    double rightMotor;
    double leftMoror;
    
    Servo leftClaw;
    Servo rightClaw;
    
   @Override
   public void init() {
     rightMotor=hardwereMap.get(DcMotor.class, "right_motor");
     leftMotor=hardweareMAp.get(DcMotor.class, "left_motor");
     
     rightClaw=hardweareMAp.servo.get("right_claw");
     leftClaw=hardweareMap.servo.get("left_claw");
      
     rigthMotor.setDirection(DcMotor.Direction.REVERSE);
     leftMotor.setDirection(DcMotor.Direction.FORWARD);
    }
    
    
    @Override
    public void loop() {
      rigthWheelPower=gamepad1.right_stick_y;
      leftWheelPower=gamepad1.left_stick_y;
      
      rightMotor.setPower(rightWheelPower);
      leftMotor.setPower(leftWheelPower);
      
      if (gamepad1.x) {
        rightClaw.setPosition(1);
        leftClaw.setPosition(1);
      }
      
      else{
        rightClaw.setPosition(0);
        leftClaw.setPosition(0);
      }
    }
     
