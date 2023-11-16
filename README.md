def newton_raphson(f, df, x0, tol=1e-5):
  """
  Mencari solusi persamaan non linier menggunakan metode Newton-Raphson.

  Args:
    f: Fungsi persamaan non linier.
    df: Turunan pertama fungsi persamaan non linier.
    x0: Nilai awal.
    tol: Toleransi.

  Returns:
    Nilai solusi x.
  """

  x = x0
  while True:
    x_new = x - f(x) / df(x)
    if abs(x_new - x) < tol:
      break
    x = x_new
  return x


def f(x):
  return x ** 3 - 2 * x ** 2 - 3 * x + 2


def df(x):
  return 3 * x ** 2 - 4 * x - 3


if __name__ == "__main__":
  x = newton_raphson(f, df, 1)
  print(f"Solusi persamaan non linier: x = {x}")
