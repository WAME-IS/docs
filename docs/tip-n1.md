# Rychly tip

Ak pracujete s DB a mate v nej stlpec s nazvom `status` a riadok, kde je status na hodnote `0`, zmente to na ine cislo! Inak nedostanete ziadne data, ktore su v databaze. Je to preto, lebo v `Core` module je konfigurovane, ze data, ktore maju hodnotu statusu na `0`, budu automaticky ignorovane.