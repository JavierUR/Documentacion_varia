# Microphone Noise Cancellation
Pulse audio comes with a module to remove echo and noise using the internal microphone

## Configuration

Load module in pulse config `/etc/pulse/default.pa`
* Add `load-module module-echo-cancel` at the end
* Reload config `pulseaudio -k`
* Select new recording device with noise cancellation in system settings
