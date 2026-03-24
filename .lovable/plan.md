

# Remove Branding & AI Source References

## Summary
Remove all "Built for INTUition 2026" text, the entire AI Brain Monitor section, and all Local/Cloud AI badges from the app.

## Changes

### 1. `src/pages/Settings.tsx`
- Remove lines 414-416 ("Built for INTUition 2026" paragraph)

### 2. `src/components/AIBrainMonitor.tsx`
- Delete this entire file

### 3. `src/pages/Home.tsx`
- Remove import of `AIBrainMonitor` and its type
- Remove `aiBrainStats` state and `trackAIDecision` helper
- Remove `lastAiDecision` state
- Remove `<AIBrainMonitor stats={aiBrainStats} />` from JSX
- Remove `aiDecision={lastAiDecision}` prop from `VisualAlert`
- Remove `trackAIDecision` calls from `handleAutoDetectedAlert` and `handleFalseAlarmFiltered`
- Simplify toast in `handleFalseAlarmFiltered` to remove Local/Cloud AI mention
- Remove `Brain` icon import (replace monitoring card icon with `Shield`)

### 4. `src/components/VisualAlert.tsx`
- Remove `aiDecision` from props interface
- Remove the AI Decision Badge JSX block (lines ~113-128)

### 5. `src/hooks/useSmsNotification.ts`
- Remove `aiBadge` construction and usage from toast descriptions (lines ~163-165, ~174-176)
- Remove `aiDecision` parameter from `notifyEmergencyContacts`

### 6. `src/services/hybridAIService.ts`
- Remove the "MOCK LOGIC - Will be replaced with real FunctionGemma + Gemini hybrid AI brain" comment
- Keep `aiSource` field in the interface/logic (internal use) but it won't be displayed anywhere

### 7. `README.md`
- Remove the "Built For INTUition 2026" section (lines ~109-113)

