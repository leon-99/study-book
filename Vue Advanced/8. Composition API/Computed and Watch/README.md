# Computed and Watch

## Introduction
The `computed` and `watch` functions in Vue.js are part of the Composition API and are used to derive and observe state changes. `computed` is used for derived state, while `watch` is used for side effects.

## Real-Life Example
Think of a weather app. The temperature in Celsius (state) can be derived as Fahrenheit (computed), and alerts can be triggered when the temperature exceeds a threshold (watch).

## Code Example
```javascript
import { ref, computed, watch } from 'vue';

const count = ref(0);

const doubleCount = computed(() => count.value * 2);

watch(count, (newValue, oldValue) => {
  console.log(`Count changed from ${oldValue} to ${newValue}`);
});
```

## Problems It Solves
- **Derived State**: Simplifies the calculation of derived values.
- **State Observation**: Monitors state changes and triggers side effects.
- **Reactivity**: Enhances the reactivity system with additional capabilities.

## Real-Life Usage
`computed` and `watch` are used in:
- **Forms**: Validating inputs and displaying error messages.
- **Dashboards**: Calculating and displaying derived metrics.
- **E-commerce**: Monitoring cart state and updating totals.

## Pros and Cons
### Pros
- Simplifies the management of derived state and side effects.
- Enhances code readability and maintainability.
- Integrates seamlessly with the Composition API.

### Cons
- Requires understanding of Vue's reactivity system.
- Can lead to performance issues if overused.

## Conclusion
The `computed` and `watch` functions are powerful tools in Vue.js for managing derived state and side effects. By leveraging these functions, developers can build dynamic and responsive applications.
