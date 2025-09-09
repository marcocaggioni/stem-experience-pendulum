# 🕰️ Galileo and the Pendulum

Galileo Galilei, the renowned Italian scientist, is credited with discovering the remarkable properties of the pendulum in the late 16th century. 🧐 Galileo first noticed the regular motion of a swinging chandelier in a cathedral and, with careful observation, realized that each swing took the same amount of time. This discovery helped lay the foundation for modern science and timekeeping! ⏳

---

# 🧪 Material for the Experiment

## 🟦 2 Micro:bit

> 💡 **Tip:**  
> You’ll need two micro:bits for the experiment 😅  
> You can find some friends to share the investment and the experience! 🤝
> Amazon link [Microbit](https://www.amazon.com/KEYESTUDIO-Micro-Original-Microbit-Starter/dp/B0BP1J72RR/) 

[![Micro:bit](https://github.com/user-attachments/assets/a3136c34-d910-4ae3-b0d4-43e834026d69)](https://microbit.org/get-started/what-is-the-microbit/)

> The micro:bit is a pocket-sized computer that introduces you to how software and hardware work together.  
> [Read more at microbit.org](https://microbit.org/get-started/what-is-the-microbit/)

---

## 🖨️ 3D Printed Case

[![3D Printed Case](https://github.com/user-attachments/assets/d3c15658-07e5-433d-9cf0-a36e493241d5)](https://makerworld.com/en/models/657713-micro-bit-v2-case-with-aaa-battery-compartment?from=search#profileId-584816)

You can use a 3D printed case to securely hold the micro:bit and its battery. For example, see this model:  
[Micro:bit V2 Case with AAA Battery Compartment on MakerWorld](https://makerworld.com/en/models/657713-micro-bit-v2-case-with-aaa-battery-compartment?from=search#profileId-584816)

---

# 🚀 Setting Up the Experiment

Let’s get started with a fun experiment to discover how a pendulum moves—just like Galileo did! 🕵️‍♂️  
You’ll use two micro:bits for this activity, and each one has a special job.

---

## 📝 What You Need

- **Micro:bit 1:** This one will ride on your pendulum! 🏄‍♂️ Put it in a 3D printed case (with two AAA batteries) and hang it on a string so it can swing back and forth. 🪢
- **Micro:bit 2:** This one stays safely connected to your computer using a USB cable. 🖥️ It will “listen” for signals from the swinging micro:bit and show you what is happening!

---

## 🤔 How Does it Work?

- **Micro:bit 1** measures how much it’s speeding up or slowing down (that’s called “acceleration” 🚀), how bright the light is (💡), and how loud the sounds are (🔊). It sends all this information through the air using radio waves! 📡
- **Micro:bit 2** waits for these messages and then draws a graph on your computer, so you can see exactly what’s happening while the pendulum swings! 📈

> ℹ️ **Did you know?**  
> When the pendulum micro:bit sends an acceleration value of `980`, that means the real acceleration is **9.8 m/s²** (the same as gravity on Earth! 🌍)

---

## 💻 Coding Your Micro:bits

### 📟 Code for the Pendulum Micro:bit (Micro:bit 1)

Copy and paste this code into the MakeCode editor for your first micro:bit (the one on the string):

[![Pendulum Microbit Code](https://github.com/user-attachments/assets/d85d1e2b-70f6-408f-bac2-f1a6168959a0)](https://makecode.microbit.org/)

```typescript
radio.setGroup(1)
basic.forever(function () {
    radio.sendValue("acceleration", input.acceleration(Dimension.Strength))
    radio.sendValue("light", input.lightLevel())
    radio.sendValue("noise", input.soundLevel())
})
```

This code tells the micro:bit to:
- 📻 Join a radio group (so it can “talk” to its partner)
- 📡 Send out its acceleration, light, and noise data over and over again

---

### 📟 Code for the Receiver Micro:bit (Micro:bit 2)

For the second micro:bit (plugged into your computer), use this code:

[![Receiver Microbit Code](https://github.com/user-attachments/assets/d7b9b30d-3ea2-495c-8b29-634462baef37)](https://makecode.microbit.org/)

```typescript
radio.onReceivedNumber(function (receivedNumber) {
    serial.writeValue("acceleration", receivedNumber)
})
radio.setGroup(1)
serial.redirectToUSB()
```

This code tells the micro:bit to:
- 👂 Listen for acceleration values from the first micro:bit
- 📨 Send those values straight to your computer, where you can graph them

---

## 🏁 Getting Ready to Experiment

1. Hang Micro:bit 1 (with batteries) on your string pendulum. 🪢
2. Insert the batteries and make sure the micro:bit is turned on. 🔋
3. Plug Micro:bit 2 into your computer’s USB port. 🖥️
4. Download and upload the correct code to each micro:bit. 💾
5. Start swinging the pendulum and watch the data appear as a graph on your computer! 📊

---

🎉 **Enjoy exploring science like Galileo—with a digital twist!** ⚡

![Galileo Cartoon](https://github.com/user-attachments/assets/876f62f5-ba54-47b3-a3ee-df9a7c80d802)
