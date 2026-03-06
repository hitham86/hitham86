import { useState, useEffect } from "react";

export default function HithamProfile() {
  const [loaded, setLoaded] = useState(false);
  useEffect(() => { setTimeout(() => setLoaded(true), 100); }, []);

  const techs = [
    { label: "Python", color: "#3776ab" },
    { label: "JavaScript", color: "#f7df1e" },
    { label: "HTML", color: "#e34f26" },
    { label: "CSS", color: "#264de4" },
    { label: "MySQL", color: "#00758f" },
    { label: "Go", color: "#00acd7" },
    { label: "Swift", color: "#fa7343" },
    { label: "Git / GitHub", color: "#aaaaaa" },
    { label: "VS Code", color: "#007acc" },
  ];

  const builds = [
    "AI-powered web apps & automation tools",
    "Django & full-stack systems",
    "Business dashboards & data pipelines",
    "Trading, finance & analytics apps",
    "Custom tools for real businesses",
  ];

  const fadeStyle = (delay) => ({
    opacity: loaded ? 1 : 0,
    transform: loaded ? "translateY(0)" : "translateY(18px)",
    transition: `opacity 0.6s ${delay}s ease, transform 0.6s ${delay}s ease`,
  });

  return (
    <div style={{
      background: "#0a0a0f",
      minHeight: "100vh",
      fontFamily: "'Segoe UI', system-ui, sans-serif",
      color: "#e8e8f0",
      padding: "0",
      position: "relative",
    }}>
      {/* Grid background */}
      <div style={{
        position: "fixed", inset: 0, zIndex: 0,
        backgroundImage: "linear-gradient(rgba(124,106,255,0.05) 1px, transparent 1px), linear-gradient(90deg, rgba(124,106,255,0.05) 1px, transparent 1px)",
        backgroundSize: "40px 40px",
        pointerEvents: "none",
      }} />

      <div style={{ position: "relative", zIndex: 1, maxWidth: 760, margin: "0 auto", padding: "48px 24px" }}>

        {/* HERO */}
        <div style={{ marginBottom: 44, ...fadeStyle(0) }}>
          <div style={{ fontSize: "clamp(2rem,6vw,3rem)", fontWeight: 800, letterSpacing: "-0.02em", lineHeight: 1.1, marginBottom: 8 }}>
            <span style={{ display: "inline-block", animation: "wave 2s ease-in-out infinite" }}>👋</span>{" "}
            Hello, I'm{" "}
            <span style={{ background: "linear-gradient(135deg,#7c6aff,#00e5ff)", WebkitBackgroundClip: "text", WebkitTextFillColor: "transparent" }}>
              Hitham
            </span>
          </div>
          <div style={{ display: "flex", alignItems: "center", gap: 8, marginBottom: 20 }}>
            <div style={{ width: 24, height: 1, background: "#00e5ff" }} />
            <span style={{ fontFamily: "monospace", fontSize: "0.8rem", color: "#00e5ff", letterSpacing: "0.15em", textTransform: "uppercase" }}>
              Python Developer
            </span>
          </div>

          {/* Badges */}
          <div style={{ display: "flex", flexWrap: "wrap", gap: 8 }}>
            {[
              { label: "Yahoo", bg: "rgba(96,1,210,0.2)", border: "#6001d2", color: "#b388ff", href: "mailto:hithamhauter@yahoo.com" },
              { label: "Gmail", bg: "rgba(209,72,54,0.2)", border: "#d14836", color: "#ff8a73", href: "mailto:hithamhauter5@gmail.com" },
              { label: "GitHub", bg: "rgba(255,255,255,0.05)", border: "#444", color: "#ccc", href: "https://github.com/hitham86" },
              { label: "LinkedIn", bg: "rgba(0,119,181,0.2)", border: "#0077b5", color: "#64b5f6", href: "https://linkedin.com/in/hitham-hauter" },
            ].map(b => (
              <a key={b.label} href={b.href} target="_blank" rel="noreferrer" style={{
                display: "flex", alignItems: "center", gap: 6,
                padding: "6px 14px", borderRadius: 6,
                fontFamily: "monospace", fontSize: "0.72rem", fontWeight: 700,
                letterSpacing: "0.05em", textTransform: "uppercase", textDecoration: "none",
                background: b.bg, border: `1px solid ${b.border}`, color: b.color,
                transition: "all 0.2s",
              }}
                onMouseEnter={e => { e.currentTarget.style.transform = "translateY(-2px)"; e.currentTarget.style.filter = "brightness(1.3)"; }}
                onMouseLeave={e => { e.currentTarget.style.transform = ""; e.currentTarget.style.filter = ""; }}
              >
                {b.label}
              </a>
            ))}
          </div>
        </div>

        <Divider />

        {/* ABOUT */}
        <Section title="🙋‍♂️ About Me" delay={0.1} loaded={loaded}>
          <p style={{ fontSize: "0.95rem", lineHeight: 1.8, color: "#a0a0c0", borderLeft: "2px solid #7c6aff", paddingLeft: 16 }}>
            Developer passionate about <B>Python</B>, <B>JavaScript</B>, <B>SQL</B>, <B>Golang</B>, and <B>Swift</B>.<br />
            Always eager to learn new technologies and solve challenging problems.<br />
            Driven by curiosity and a love for building things that matter.
          </p>
        </Section>

        <Divider />

        {/* CURRENTLY */}
        <Section title="🔍 Currently" delay={0.15} loaded={loaded}>
          <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit,minmax(180px,1fr))", gap: 12 }}>
            {[
              { icon: "🔭", text: <>Building <B>Python Projects</B> focused on automation & data</> },
              { icon: "🌱", text: <>Deepening skills in <B>AI</B> & <B>Data Science</B></> },
              { icon: "💬", text: <>Happy to chat about <B>Programming</B> & <B>SQL</B></> },
            ].map((c, i) => (
              <div key={i} style={{ background: "#13131e", border: "1px solid #1e1e2e", borderRadius: 10, padding: 16, transition: "all 0.2s" }}
                onMouseEnter={e => { e.currentTarget.style.borderColor = "#7c6aff"; e.currentTarget.style.transform = "translateY(-2px)"; }}
                onMouseLeave={e => { e.currentTarget.style.borderColor = "#1e1e2e"; e.currentTarget.style.transform = ""; }}
              >
                <div style={{ fontSize: "1.3rem", marginBottom: 8 }}>{c.icon}</div>
                <p style={{ fontSize: "0.82rem", color: "#6b6b8a", lineHeight: 1.5 }}>{c.text}</p>
              </div>
            ))}
          </div>
        </Section>

        <Divider />

        {/* TECH */}
        <Section title="⚒️ Languages, Frameworks & Tools" delay={0.2} loaded={loaded}>
          <div style={{ display: "flex", flexWrap: "wrap", gap: 10 }}>
            {techs.map(t => (
              <div key={t.label} style={{
                display: "flex", alignItems: "center", gap: 7,
                background: "#13131e", border: "1px solid #1e1e2e", borderRadius: 8,
                padding: "8px 14px", fontFamily: "monospace", fontSize: "0.75rem", color: "#6b6b8a",
                transition: "all 0.2s", cursor: "default",
              }}
                onMouseEnter={e => { e.currentTarget.style.borderColor = "#7c6aff"; e.currentTarget.style.color = "#e8e8f0"; e.currentTarget.style.transform = "translateY(-2px)"; }}
                onMouseLeave={e => { e.currentTarget.style.borderColor = "#1e1e2e"; e.currentTarget.style.color = "#6b6b8a"; e.currentTarget.style.transform = ""; }}
              >
                <span style={{ width: 7, height: 7, borderRadius: "50%", background: t.color, flexShrink: 0, display: "inline-block" }} />
                {t.label}
              </div>
            ))}
          </div>
        </Section>

        <Divider />

        {/* WHAT I BUILD */}
        <Section title="🚀 What I Build" delay={0.25} loaded={loaded}>
          <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 10 }}>
            {builds.map((b, i) => (
              <div key={i} style={{
                background: "#13131e", border: "1px solid #1e1e2e", borderRadius: 8,
                padding: "12px 16px", fontSize: "0.85rem", color: "#9090b0",
                display: "flex", alignItems: "center", gap: 10, transition: "all 0.2s",
              }}
                onMouseEnter={e => { e.currentTarget.style.borderColor = "#00e5ff"; e.currentTarget.style.color = "#e8e8f0"; e.currentTarget.style.transform = "translateX(3px)"; }}
                onMouseLeave={e => { e.currentTarget.style.borderColor = "#1e1e2e"; e.currentTarget.style.color = "#9090b0"; e.currentTarget.style.transform = ""; }}
              >
                <span style={{ color: "#00e5ff", fontFamily: "monospace", fontSize: "0.8rem", flexShrink: 0 }}>→</span>
                {b}
              </div>
            ))}
          </div>
        </Section>

        <Divider />

        {/* CONTACT */}
        <Section title="📫 Contact Me" delay={0.3} loaded={loaded}>
          <div style={{ display: "flex", flexWrap: "wrap", gap: 12 }}>
            {[
              { label: "hithamhauter@yahoo.com", href: "mailto:hithamhauter@yahoo.com" },
              { label: "hithamhauter5@gmail.com", href: "mailto:hithamhauter5@gmail.com" },
              { label: "linkedin.com/in/hitham-hauter", href: "https://linkedin.com/in/hitham-hauter" },
            ].map(c => (
              <a key={c.label} href={c.href} target="_blank" rel="noreferrer" style={{
                display: "flex", alignItems: "center", gap: 8,
                background: "#13131e", border: "1px solid #1e1e2e", borderRadius: 8,
                padding: "10px 16px", fontSize: "0.82rem", color: "#6b6b8a",
                textDecoration: "none", fontFamily: "monospace", transition: "all 0.2s",
              }}
                onMouseEnter={e => { e.currentTarget.style.borderColor = "#7c6aff"; e.currentTarget.style.color = "#7c6aff"; }}
                onMouseLeave={e => { e.currentTarget.style.borderColor = "#1e1e2e"; e.currentTarget.style.color = "#6b6b8a"; }}
              >
                {c.label}
              </a>
            ))}
          </div>
        </Section>

        {/* CALLOUT */}
        <div style={{
          marginTop: 40,
          background: "linear-gradient(135deg,rgba(124,106,255,0.08),rgba(0,229,255,0.06))",
          border: "1px solid rgba(124,106,255,0.3)",
          borderRadius: 10, padding: "16px 20px",
          fontSize: "0.875rem", color: "#a0a0c0", fontStyle: "italic",
          display: "flex", alignItems: "center", gap: 12,
          ...fadeStyle(0.35),
        }}>
          <span style={{ fontSize: "1.2rem", fontStyle: "normal" }}>💡</span>
          Open to collaboration, learning, and new opportunities — feel free to reach out!
        </div>
      </div>

      <style>{`
        @keyframes wave {
          0%, 100% { transform: rotate(0deg); }
          25% { transform: rotate(20deg); }
          75% { transform: rotate(-10deg); }
        }
      `}</style>
    </div>
  );
}

function Divider() {
  return <div style={{ height: 1, background: "linear-gradient(90deg,transparent,#1e1e2e,#1e1e2e,transparent)", margin: "28px 0" }} />;
}

function Section({ title, children, delay, loaded }) {
  return (
    <div style={{
      marginBottom: 36,
      opacity: loaded ? 1 : 0,
      transform: loaded ? "translateY(0)" : "translateY(18px)",
      transition: `opacity 0.6s ${delay}s ease, transform 0.6s ${delay}s ease`,
    }}>
      <div style={{
        display: "flex", alignItems: "center", gap: 10, marginBottom: 16,
        fontFamily: "monospace", fontSize: "0.85rem", fontWeight: 700,
        letterSpacing: "0.08em", textTransform: "uppercase", color: "#6b6b8a",
      }}>
        {title}
        <div style={{ flex: 1, height: 1, background: "#1e1e2e" }} />
      </div>
      {children}
    </div>
  );
}

function B({ children }) {
  return <strong style={{ color: "#e8e8f0", fontWeight: 500 }}>{children}</strong>;
}
