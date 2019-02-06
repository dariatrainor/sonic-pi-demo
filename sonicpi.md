# Cheatsheet for Sonic Pi

## 1. Play a note

```
play 50
```

Sleep

```
play 50
sleep 1
play 55
sleep 1
play 62
```

As an array

```
play [50, 55, 62]
```

Notes

```
play :c3
sleep 1
play :d3
sleep 1
play :e3
```

Chord 

```
play chord(:E3, :minor)
```

Sound and release

```
play :c3, amp: 0.3, release: 0.5
sleep 1
play :d3, amp: 0.7, release: 1
sleep 1
play :e3, amp: 10.0, release: 2
```

Scales

```
play_pattern_timed scale(:c3, :major), 0.3, release: 0.5
```

Patterned Array

```
play_pattern_timed [:C3, :C3, :G3, :G3, :A3, :A3], 0.5, release: 0.5
play :G3, release: 1
```

Synth

```
use_synth :prophet
use_synth :dark_ambience
use_synth :piano
```

BPM

```
use_bpm 120
```

Loop

```
4.times do
end
```

Infinite loop

```
loop do
  play 60
  sleep 1
end
```

Live loop

```
live_loop :drums do
  sample :drum_heavy_kick
  sleep 1
  sample :drum_snare_hard
  sleep 1
  sample :drum_heavy_kick
  sleep 1
  sample :drum_snare_hard
  sleep 1
end
```

Sample

```
live_loop :hihat do
  sample :drum_cymbal_closed
  sleep 0.25
end
```

Choose

```
live_loop :melody do
  play chord(:E3, :minor).choose, amp: 0.25, release: 0.25
  sleep 0.25
end
```

