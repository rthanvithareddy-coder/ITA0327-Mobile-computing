current_signal = -80
hysteresis = 5

neighbor_signals = [-78, -75, -70, -82, -65]

current_station = "Base Station 1"

print("Handoff Simulation with Hysteresis")

for signal in neighbor_signals:

    print("\nCurrent Signal:", current_signal)
    print("Neighbor Signal:", signal)

    if signal > current_signal + hysteresis:

        current_station = "Base Station 2"
        current_signal = signal

        print("Handoff Successful!")
        print("Connected to:", current_station)

    else:
        print("No Handoff Required")
        current_signal = max(current_signal, signal)

print("\nFinal Connected Station:", current_station)
