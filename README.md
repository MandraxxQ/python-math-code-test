import sympy as sp import numpy as np

def derivative(expr, var): return sp.diff(expr, var)

def integral(expr, var): return sp.integrate(expr, var)

def definite_integral(expr, var, a, b): return sp.integrate(expr, (var, a, b))

def taylor_series(expr, var, a, n): return sp.series(expr, var, a, n).removeO()

def solve_equation(equation, var): return sp.solve(equation, var)

def evaluate_expression(expr, values): return expr.subs(values).evalf()

def limit(expr, var, a): return sp.limit(expr, var, a)

def laplace_transform(expr, var, s): return sp.laplace_transform(expr, var, s)[0]

def fourier_transform(expr, var, k): return sp.fourier_transform(expr, var, k)

def numerical_integration(expr, var, a, b): f = sp.lambdify(var, expr, 'numpy') return np.trapz([f(xi) for xi in np.linspace(a, b, 100)], np.linspace(a, b, 100))

if name == "main": x, s, k = sp.symbols('x s k') expr = sp.sin(x) / x

print("Выражение:", expr)
print("Производная:", derivative(expr, x))
print("Интеграл:", integral(expr, x))
print("Определенный интеграл от 0 до π:", definite_integral(expr, x, 0, sp.pi))
print("Ряд Тейлора (n=5):", taylor_series(expr, x, 0, 5))
print("Решение уравнения x^2 - 4 = 0:", solve_equation(sp.Eq(x**2 - 4, 0), x))
print("Численное значение при x=1:", evaluate_expression(expr, {x: 1}))
print("Предел при x → 0:", limit(expr, x, 0))
print("Преобразование Лапласа sin(x)/x:", laplace_transform(expr, x, s))
print("Преобразование Фурье sin(x)/x:", fourier_transform(expr, x, k))
print("Численный интеграл от 0 до π:", numerical_integration(expr, x, 0, np.pi))

#код тест на Python
#это что высшая математика ого воу ее
#библиотеки нужна йоу
