# Mime Party

Charades, Pictionary, or both — a live party game for 4–20 people. Media and game state go peer-to-peer (WebRTC). A public PeerJS broker only introduces peers, the same idea VDO.Ninja uses: no game server to host, no accounts.

## Play

1. On GitHub: **Settings → Pages → Deploy from branch → `main` / root → Save**.
2. Open `https://tbenitz.github.io/mime-party/` (or open `index.html` from any static host on HTTPS — camera and mic need a secure origin).
3. One person creates the party and shares the room code.
4. Everyone else joins with that code. Four players minimum, twenty maximum.

The party leader’s browser is the referee. If they close the tab, the room pauses until they reopen it and reclaim the same code (the code is saved in this browser).

## Rules built in

- Each turn is **Charades**, **Pictionary**, or **Combo** (act and draw).
- The actor and the **opposing team** see the secret. The guessing team does not.
- Anyone can buzz a correct guess. The actor or party leader confirms the point.
- **Challenge** if someone says the word, spells it, points, or cheats. Everyone votes. If the room agrees, the party leader confirms; if it splits, the party leader picks the outcome (no point, award, steal, or −1).
- Scores stick to the person, not the tab. Leave and come back with the same browser and you reclaim your seat, team, and points.

## Network notes

Signaling uses PeerJS Cloud (`0.peerjs.com`). Audio/video/drawing travel directly between browsers. Symmetric NATs can block video without a TURN server; the word, drawing, score, and challenge flow still work over the data channel. Watching one actor from many tabs means that actor uploads one stream per viewer — fine for a living-room party, heavier at 20 remote viewers.

## License

MIT
