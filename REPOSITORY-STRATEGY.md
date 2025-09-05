# NEXUS Repository Management Strategy

## Phase Separation Rationale
Phase I and Phase II are maintained in separate repositories to ensure:
- Production stability (Phase I remains frozen)
- Independent development cycles
- Risk isolation
- Clear handoff boundaries for USDA

## Repository Mapping
| Repository | Purpose | Status | Version |
|------------|---------|--------|---------|
| `nexus-development-1` | Phase I Production | Frozen | 1.x.x |
| `nexus-phase-2` | Phase II Development | Active | 2.x.x |
| `usda-infrastructure` | Shared Infrastructure | Active | N/A |

## Development Workflow

### Phase I (nexus-development-1)
- **Hotfixes only** via `hotfix/*` branches
- No new features
- Maintain 1.x.x versioning

### Phase II (nexus-phase-2)
- **Active development** on `develop` branch
- Feature branches: `feature/*`
- Version 2.x.x

### Integration Points
- Infrastructure shared via `usda-infrastructure`
- APIs versioned independently
- Database migrations coordinated

## Migration Strategy
1. Phase II starts with Phase I snapshot
2. Independent evolution during development
3. Potential future consolidation post-USDA handoff
