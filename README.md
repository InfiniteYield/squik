# 🍳 What is Squik?

**Squik** is a UI state management system for Roblox that keeps things simple.

It doesn’t try to be React. It doesn’t try to reinvent Lua. It’s built *specifically* for people who like how Roblox works — and just want a cleaner way to manage UI.

---

# 🧠 The Philosophy

**Squik is for people who hate React.**

Not in a “we’ll copy React and call it something else” way. In a “seriously, I just want to update my UI without writing a state manager from scratch every project” way.

If you've ever thought:
- “Why do I need a virtual DOM to change a text label?”
- “Why does this feel like JavaScript pretending to be Luau?”
- “Can I just write something that *works*?”

Then you're in the right place.

---

# 🧱 How It Works (but not in a weird way)

Squik is built around two ideas:
1. **A "Space" is a little UI brain.** It controls a UI object (`TextLabel`, `Frame`, whatever), and it knows how to render itself when its data (called `Props`) changes.
2. **You don’t manually update the UI.** You just change `Props`, and Squik reruns the function for you. That’s it.

No virtual trees, no weird lifecycle junk, no JSX.

---

# 🧩 What It Gives You

- **A way to manage UI modules with state.** Each one handles its own logic.
- **Automatic cleanup.** All your event connections and threads are cleaned up when stuff changes.
- **Easy to nest.** Spaces can be inside other Spaces. If a parent updates, the kids update too.
- **Props are reactive.** Change a value like `Props.Count = 1`, and the component rerenders.

It’s like Roact if it stopped trying to be React and just embraced Roblox.

---

# 🧪 What It Looks Like

```lua
return function(Space, Props)
	local Button = Space.UI
	Button.Text = "Clicks: " .. (Props.Count or 0)

	Space:Connect(Button.MouseButton1Click, function()
		Props.Count = (Props.Count or 0) + 1
	end)
end
```

Simple, readable, no magic — just works.

---

# 🛠️ Why You Might Actually Use It

- You hate writing spaghetti event code but also hate JSX.
- You like Roblox's UI system but want something more structured.
- You’ve tried Roact and thought, *“cool idea, but why do I need 300 lines for a menu?”*
- You’re building menus, editors, HUDs, whatever — and want the code to be easy to reason about.

---

# 🧬 What Squik Isn’t

- It's **not** a virtual DOM.
- It doesn’t want to simulate web dev.
- It doesn’t replace how Roblox works — it *just plays nicer* with it.

---

If you like scripting more than configuring, and you're tired of frameworks trying to be too clever, **Squik** is gonna feel like home.

