# Tugas 12 PBO

Nama  : Muhammad Irsyad Habibi
NRP  : 5025221150
Kelas  : PBO A

# Class Ticket

```
abstract class Ticket {
    protected double baseFare;

    public Ticket(double baseFare) {
        this.baseFare = baseFare;
    }

    // Abstract method untuk menghitung tarif
    public abstract double calculateFare();

    // Method untuk mendapatkan detail umum tiket
    public String getDetails() {
        return "Base Fare: $" + baseFare;
    }
}
```
- Berisi atribut dasar baseFare (harga dasar).
- Memiliki metode abstrak calculateFare() yang wajib diimplementasikan oleh subclass.
- Metode getDetails() untuk menampilkan informasi umum tiket.

# Subclass EconomyTicket

```
class EconomyTicket extends Ticket {
    public EconomyTicket(double baseFare) {
        super(baseFare);
    }

    @Override
    public double calculateFare() {
        return baseFare * 0.9; // Diskon 10%
    }

    @Override
    public String getDetails() {
        return super.getDetails() + ", Final Fare: $" + calculateFare() + " (Economy Class)";
    }
}
```
- Mengimplementasikan metode calculateFare() dengan diskon 10%.
- Menambahkan detail tentang kelas tiket di getDetails().

# Subclass BusinessTicket

```
class BusinessTicket extends Ticket {
    public BusinessTicket(double baseFare) {
        super(baseFare);
    }

    @Override
    public double calculateFare() {
        return baseFare * 1.25; // Tambahan biaya 25%
    }

    @Override
    public String getDetails() {
        return super.getDetails() + ", Final Fare: $" + calculateFare() + " (Business Class)";
    }
}
```
- Mengimplementasikan metode calculateFare() dengan tambahan biaya 25%.
- Menambahkan detail tentang kelas tiket di getDetails().
# Subclass FirstClassTicket

```
class FirstClassTicket extends Ticket {
    public FirstClassTicket(double baseFare) {
        super(baseFare);
    }

    @Override
    public double calculateFare() {
        return baseFare * 1.5; // Tambahan biaya 50%
    }

    @Override
    public String getDetails() {
        return super.getDetails() + ", Final Fare: $" + calculateFare() + " (First Class)";
    }
}
```
- Mengimplementasikan metode calculateFare() dengan tambahan biaya 50%.
- Menambahkan detail tentang kelas tiket di getDetails().
# Main Class

```
public class Main {
    public static void main(String[] args) {
        // Contoh penggunaan
        Ticket economyTicket = new EconomyTicket(100.0);
        Ticket businessTicket = new BusinessTicket(100.0);
        Ticket firstClassTicket = new FirstClassTicket(100.0);

        // Menampilkan detail tiket
        System.out.println(economyTicket.getDetails());
        System.out.println(businessTicket.getDetails());
        System.out.println(firstClassTicket.getDetails());
    }
}
```

Contoh output:
```
Base Fare: $100.0, Final Fare: $90.0 (Economy Class)
Base Fare: $100.0, Final Fare: $125.0 (Business Class)
Base Fare: $100.0, Final Fare: $150.0 (First Class)

```
