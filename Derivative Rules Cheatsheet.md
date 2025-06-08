# Derivative Rules Cheatsheet

## 1. Power Rule
**Formula**: $(\frac{d}{dx} x^n = n x^{n-1})$

**Use When**: You are differentiating a term like $x^n$ where $n$ is a constant.

## 2. Constant Multiple Rule
**Formula**: $(\frac{d}{dx} [c \cdot f(x)] = c \cdot \frac{d}{dx} f(x))$

**Use When**: You have a constant multiplied by a function.

## 3. Sum Rule
**Formula**: $(\frac{d}{dx} [f(x) + g(x)] = \frac{d}{dx} f(x) + \frac{d}{dx} g(x))$

**Use When**: You are differentiating a sum of functions.

## 4. Difference Rule
**Formula**: $(\frac{d}{dx} [f(x) - g(x)] = \frac{d}{dx} f(x) - \frac{d}{dx} g(x))$

**Use When**: You are differentiating a difference of functions.

## 5. Product Rule
**Formula**: $(\frac{d}{dx} [f(x) \cdot g(x)] = f'(x) g(x) + f(x) g'(x))$

**Use When**: You are differentiating a product of two functions.

## 6. Quotient Rule
**Formula**: $(\frac{d}{dx} \left[\frac{f(x)}{g(x)}\right] = \frac{f'(x) g(x) - f(x) g'(x)}{g(x)^2})$

**Use When**: You are differentiating a quotient of two functions.

## 7. Chain Rule
**Formula**: $(\frac{d}{dx} f(g(x)) = f'(g(x)) \cdot g'(x))$

**Use When**: You are differentiating a composite function, i.e., a function inside another function.

# Applying the Rules: Step-by-Step Guide

1. **Identify the structure of the function**: Look at the form of the function you need to differentiate. Is it a single term, a sum, a product, a quotient, or a composite function?

2. **Choose the appropriate rule(s)**:
    - If the function is a single term like $x^n$, use the **Power Rule**.
    - If the function includes constants multiplied by terms, use the **Constant Multiple Rule**.
    - If the function is a sum or difference of functions, use the **Sum Rule** or **Difference Rule**.
    - If the function is a product of two functions, use the **Product Rule**.
    - If the function is a quotient of two functions, use the **Quotient Rule**.
    - If the function is a composite of functions (a function inside another function), use the **Chain Rule**.

3. **Break down complex functions**: For complex functions, you might need to apply multiple rules. Start by breaking the function into simpler parts and apply the appropriate rules step by step.

# Example Breakdown with Given Function

## Loss Function:
$$\mathcal{J}_{\vec{w}} = 40 \sin^3\left(\frac{1}{2}w_1 + w_2\right) + w_1^2 + w_2^2$$

**Identify Components**:
- $40 \sin^3\left(\frac{1}{2}w_1 + w_2\right)$: Composite function ($\sin^3(u)$ where $u = \frac{1}{2}w_1 + w_2$), requires **Chain Rule**.
- $w_1^2$ and $w_2^2$: Single terms, use **Power Rule**.

**Steps**:
1. Differentiate $40 \sin^3\left(\frac{1}{2}w_1 + w_2\right)$ with respect to $w_1$:
   - Outer function: $\sin^3(u)$, derivative is $3 \sin^2(u) \cdot \cos(u)$ (use **Chain Rule**)
   - Inner function: $u = \frac{1}{2}w_1 + w_2$, derivative is $\frac{1}{2}$ with respect to $w_1$
   - Combine: $40 \cdot 3 \sin^2\left(\frac{1}{2}w_1 + w_2\right) \cdot \cos\left(\frac{1}{2}w_1 + w_2\right) \cdot \frac{1}{2}$

2. Differentiate $w_1^2$ with respect to $w_1$:
   - Use **Power Rule**: Derivative is $2w_1$

3. Combine for $\frac{\partial \mathcal{J}}{\partial w_1}$:
   $$\frac{\partial \mathcal{J}}{\partial w_1} = 60 \sin^2\left(\frac{1}{2}w_1 + w_2\right) \cos\left(\frac{1}{2}w_1 + w_2\right) + 2 w_1$$

4. Differentiate $(40 \sin^3\left(\frac{1}{2}w_1 + w_2\right))$ with respect to $(w_2)$:
   - Outer function: Same as for $(w_1)$, but inner function derivative is $(1)$ with respect to $(w_2)$

5. Differentiate $(w_2^2)$ with respect to $(w_2)$:
   - Use **Power Rule**: Derivative is $(2w_2)$

6. Combine for $(\frac{\partial \mathcal{J}}{\partial w_2})$:
   $$\frac{\partial \mathcal{J}}{\partial w_2} = 120 \sin^2\left(\frac{1}{2}w_1 + w_2\right) \cos\left(\frac{1}{2}w_1 + w_2\right) + 2 w_2$$

# Summary of Gradient Calculation
- Identify function structure and components.
- Apply the appropriate differentiation rules (Chain, Power, Product, etc.).
- Break down complex functions and combine results step by step.
