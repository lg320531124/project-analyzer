# Project Analyzer — 8-Dimension Deep Analysis Framework

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) skill that transforms shallow code tours into **living architectural analysis**.

Most project analysis is a static specimen — precise but lifeless. It lists components, traces calls, enumerates configs. This skill produces analysis that has **Why** (design intent), **Fallback** (what happens when things break), **Closed Loop** (how the system evolves), **Competitive Landscape** (where it stands), **Quantification** (precise numbers from code), and a **time arrow** (how it changes over time).

## The 8 Dimensions

| # | Dimension | Core Question | What It Produces |
|---|-----------|--------------|-----------------|
| 1 | Progressive Disclosure | Can readers get what they need at their level? | L0/L1/L2 layered docs |
| 2 | Architecture Decision Records | Why was it designed this way? | ADR table with alternatives |
| 3 | Scenario Walkthrough | Can the architecture actually run? | 3-scenario numerical trace |
| 4 | Degradation & Fallback | What happens when it breaks? | Fallback chain table |
| 5 | Competitive Landscape | Where does this stand vs alternatives? | Comparison table |
| 6 | Quantification | Are there real numbers? | Threshold/priority tables from code |
| 7 | Closed Loop | Does the system evolve over time? | Feedback loop diagram |
| 8 | Longitudinal Narrative | What happens long-term? | Day 1/30/90 evolution table |

## Installation

### Claude Code Plugin (recommended)

Once published to the official marketplace:

```bash
/plugin install project-analyzer@claude-plugins-official
```

### Manual

Copy or symlink `skills/project-analyzer/` into your `.claude/skills/` directory:

```bash
# Option 1: Symlink
ln -s $(pwd)/skills/project-analyzer ~/.claude/skills/project-analyzer

# Option 2: Copy
cp -r skills/project-analyzer ~/.claude/skills/project-analyzer
```

Or add this repo as a plugin in your project's `.claude-plugin/plugin.json`.

## Usage

Trigger with natural language in Claude Code:

- "Analyze this project"
- "Deep dive into this repo"
- "Review the system design"
- "How does X work architecturally"
- "Understand this architecture"

## Example Output

The skill produces a structured analysis following this template:

```markdown
# {Project Name} Architecture Deep Analysis

## L0 Overview (5 minutes)
- One-sentence definition + core architecture diagram + key numbers

## L1 Architecture Detail (30 minutes)
- Component relationships + scenario walkthrough with real values

## L2 Implementation Detail (deep dive)
- Code path mapping + interface definitions

## Architecture Decision Records
| Decision | Choice | Rejected Alternative | Why |

## Degradation & Fallback
| Mechanism | Normal Path | Fallback Chain | Ultimate Backstop |

## Competitive Landscape
| Dimension | This Project | Competitor A | Competitor B |

## Closed Loops
Diagram with feedback arrows + loop labels

## Longitudinal Evolution
| Time | System State | Driving Mechanism |

## Risk Points
- Components without fallback chains
- TODO/FIXME/HACK locations
```

## Quality Checklist

Every analysis should verify:

1. ✅ Numbers come from code (thresholds traceable to source)
2. ✅ ADR has alternatives (each decision lists rejected options)
3. ✅ Scenario walkthroughs use concrete values
4. ✅ Fallback chains reach a backstop
5. ✅ Competitive comparison is fair
6. ✅ Closed loops have feedback arrows
7. ✅ Longitudinal narrative is grounded in actual mechanisms

## License

Apache-2.0
