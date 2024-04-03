# Bran


#include <iostream>
#include <cmath>

class Figura {
public:
    virtual double Pole() = 0;
};

class Kwadrat : public Figura {
public:
    double Pole(double bok) override {
        return bok * bok;
    }
};

class Prostokat : public Figura {
public:
    double Pole(double bok_a, double bok_b) override {
        return bok_a * bok_b;
    }
};

class Okrag : public Figura {
public:
    double Pole(double promien) override {
        return M_PI * pow(promien, 2);
    }
};

int main() {
    Kwadrat kwadrat;
    Prostokat prostokat;
    Okrag okrag;

    double bok_kwadratu, bok_a_prostokata, bok_b_prostokata, promien_okregu;

    std::cout << "Podaj długość boku kwadratu: ";
    std::cin >> bok_kwadratu;

    std::cout << "Podaj długość pierwszego boku prostokąta: ";
    std::cin >> bok_a_prostokata;

    std::cout << "Podaj długość drugiego boku prostokąta: ";
    std::cin >> bok_b_prostokata;

    std::cout << "Podaj promień okręgu: ";
    std::cin >> promien_okregu;

    std::cout << "Pole kwadratu: " << kwadrat.Pole(bok_kwadratu) << std::endl;
    std::cout << "Pole prostokąta: " << prostokat.Pole(bok_a_prostokata, bok_b_prostokata) << std::endl;
    std::cout << "Pole okręgu: " << okrag.Pole(promien_okregu) << std::endl;

    return 0;
}
