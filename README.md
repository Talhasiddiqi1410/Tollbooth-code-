# Tollbooth-code-
#include <iostream>

class TollBooth {
private:
  unsigned int totalCars;
  double totalCash;

public:
  TollBooth() : totalCars(0), totalCash(0.0) {}

  // Member functions to handle paying and non-paying cars
  void payingCar() {
    totalCars++;
ok    totalCash += 0.5;
  }

  void nopayCar() {
    totalCars++;
  }

  // Display function marked as const as it doesn't modify data
  void display() const {
    std::cout << "Total Cars: " << totalCars << std::endl;
    std::cout << "Total Cash: $" << totalCash << std::endl;
  }
};

int main() {
  TollBooth booth;
  char choice;

  while (true) {
    std::cout << "\nMenu:" << std::endl;
    std::cout << "(P)aying Car" << std::endl;
    std::cout << "(N)on-paying Car" << std::endl;
    std::cout << "(E)xit" << std::endl;
    std::cout << "Enter your choice: ";
    std::cin >> choice;

    switch (choice) {
      case 'P':
      case 'p':
        booth.payingCar();
        break;
      case 'N':
      case 'n':
        booth.nopayCar();
        break;
      case 'E':
      case 'e':
        booth.display();
        return 0;
      default:
        std::cout << "Invalid choice. Please try again." << std::endl;
    }
  }

  return 0;
}
