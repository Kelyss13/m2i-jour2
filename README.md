# m2i-jour2

<?php

class Perso 
{
    public const PV_INITIAL = 2000;

    private $pv;

    // Constructeur : celui-ci est appelé lors de l'instanciation de l'objet.
    // Ce constructeur possède un paramètre optionnel.
    public function __construct($pv = false) 
    {
        if (!is_numeric($pv) || $pv < 0 || $pv > 100000000) {
            $this->pv = self::PV_INITIAL;
        } else {
            $this->pv = $pv;
	}
    }

    // Accesseurs
    public function getPv() 
    {
        return $this->pv;
    }

    public function isDead() 
    {
        return $this->pv == 0;
    }
}

// Création d'une classe enfant de Perso
class Magicien extends Perso 
{
    private $magie;
}

// Création d'une instance de classe
$perso = new Perso(1000);

// Utilisation de l'objet
echo 'Votre personnage a ' . $perso->getPV() . ' PV.';;;

// Constantes de classes
echo 'Le PV par défaut attribué à un nouveau personnage est de ' . Perso::PV_INITIAL . '.';

// Destruction de l'objet
unset($perso);
