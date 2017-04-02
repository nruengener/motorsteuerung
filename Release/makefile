################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
Motorsteuerung_PWM.lss \

FLASH_IMAGE += \
Motorsteuerung_PWM.hex \

SIZEDUMMY += \
sizedummy \


# All Target
all: Motorsteuerung_PWM.elf secondary-outputs

# Tool invocations
Motorsteuerung_PWM.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,Motorsteuerung_PWM.map -Wl,-u,vfprintf -mmcu=atmega328p -o "Motorsteuerung_PWM.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

Motorsteuerung_PWM.lss: Motorsteuerung_PWM.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S Motorsteuerung_PWM.elf  >"Motorsteuerung_PWM.lss"
	@echo 'Finished building: $@'
	@echo ' '

Motorsteuerung_PWM.hex: Motorsteuerung_PWM.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex Motorsteuerung_PWM.elf  "Motorsteuerung_PWM.hex"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: Motorsteuerung_PWM.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega328p Motorsteuerung_PWM.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) Motorsteuerung_PWM.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
