# Bran
#include <iostream>
#include <cmath>

using namespace std;

class Figura {
public:
    virtual double Pole() = 0;
};

class Kwadrat : public Figura {
private:
    double bok;
public:
    Kwadrat(double b) : bok(b) {}
    double Pole() override {
        return bok * bok;
    }
};

class Prostokat : public Figura {
private:
    double bok_a, bok_b;
public:
    Prostokat(double a, double b) : bok_a(a), bok_b(b) {}
    double Pole() override {
        return bok_a * bok_b;
    }
};

class Okrag : public Figura {
private:
    double promien;
public:
    Okrag(double r) : promien(r) {}
    double Pole() override {
        return M_PI * pow(promien, 2);
    }
};

int main() {
    double bok_kwadratu, bok_a_prostokata, bok_b_prostokata, promien_okregu;

    cout << "Podaj długość boku kwadratu: ";
    cin >> bok_kwadratu;

    cout << "Podaj długość pierwszego boku prostokąta: ";
    cin >> bok_a_prostokata;

    cout << "Podaj długość drugiego boku prostokąta: ";
    cin >> bok_b_prostokata;

    cout << "Podaj promień okręgu: ";
    cin >> promien_okregu;

    Kwadrat kwadrat(bok_kwadratu);
    Prostokat prostokat(bok_a_prostokata, bok_b_prostokata);
    Okrag okrag(promien_okregu);

    cout << "Pole kwadratu: " << kwadrat.Pole() << endl;
    cout << "Pole prostokąta: " << prostokat.Pole() << endl;
    cout << "Pole okręgu: " << okrag.Pole() << endl;

    return 0;
}


