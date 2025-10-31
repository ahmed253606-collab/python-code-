# Bisection Method Implementation in Python (Google Colab Ready)

# --- Step 1: Define the Bisection Function ---
def bisection(f, a, b, tol=None, max_iter=None):
    # Check if the initial interval is valid
    if f(a) * f(b) > 0:
        print("The function has the same signs at a and b. Choose another interval.")
        return None

    print("Iter |     a     |     b     |     p     |   f(a)    |   f(b)    |   f(p)    |  Error")
    print("------------------------------------------------------------------------------------------")

    prev_p = None

    for i in range(1, (max_iter or 100) + 1):
        fa = f(a)
        fb = f(b)
        p = (a + b) / 2
        fp = f(p)

        # Error (difference between current and previous midpoint)
        error = abs(p - prev_p) if prev_p is not None else 0

        print(f"{i:4d} | {a:9.5f} | {b:9.5f} | {p:9.5f} | {fa:9.5f} | {fb:9.5f} | {fp:9.5f} | {error:7.5f}")

        # Check stopping conditions
        if tol is not None and abs(fp) < tol:
            print("\nStop: |f(p)| < tolerance =", tol)
            break
        if max_iter is not None and i >= max_iter:
            print("\nStop: reached maximum iterations =", max_iter)
            break

        # Update interval
        if fa * fp < 0:
            b = p
        else:
            a = p

        prev_p = p

    print("\nApproximate root:", p)
    return p


# --- Step 2: Define the functions you want to test ---

# Case 1: f(x) = x^3 - 3x - 1, interval [-2, 2], run 3 steps
def f1(x):
    return x**3 - 3*x - 1

print("Function 1: f(x) = x^3 - 3x - 1, interval [-2, 2]")
bisection(f1, a=-2, b=2, max_iter=3)


# Case 2: f(x) = x^3 - x - 1, interval [1, 2], until |f(p)| < 0.065
def f2(x):
    return x**3 - x - 1

print("\nFunction 2: f(x) = x^3 - x - 1, interval [1, 2]")
bisection(f2, a=1, b=2, tol=0.065)
