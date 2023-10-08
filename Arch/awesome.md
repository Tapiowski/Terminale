## Keys
awful.key({ modkey }, "r", function() awful.util.spawn("rofi -show drun") end),

awful.key({ modkey }, "w", function() awful.util.spawn("rofi -show window") end),

awful.key({ modkey }, "b", function() awful.util.spawn("firefox") end),

--- client keys ---
clientkeys = gears.table.join(
    awful.key({ modkey }, "f", function(c)
        c.fullscreen = not c.fullscreen
        c:raise()
    end),
    awful.key({ modkey }, "r", function() awful.util.spawn("rofi -show drun") end),
	awful.key({ modkey }, "w", function() awful.util.spawn("rofi -show window") end),
	awful.key({ modkey }, "b", function() awful.util.spawn("firefox") end),

## Autostart
awful.spawn("picom --experimental-backends")
awful.spawn("xscreensaver --no-splash")

--- daily fortune ---
awful.spawn.with_shell("notify-send \"$(cowsay $(fortune))\" -t 0")