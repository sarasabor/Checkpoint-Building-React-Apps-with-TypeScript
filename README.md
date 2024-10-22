# Checkpoint-Building-React-Apps-with-TypeScript


Étapes de conversion
Ajouter des types pour les props et l'état : Définir des types pour les propriétés du composant Greeting et pour l'état du composant Counter.

Utiliser les fonctionnalités de TypeScript : Adapter le code pour utiliser les types TypeScript et les classes de manière appropriée.

Corriger la syntaxe : S'assurer que la syntaxe JSX et les méthodes sont correctement écrites.

Code Converti
Code 01 : Composant Greeting
typescript
Copier le code
import React from 'react';

// Définir une interface pour les props
interface GreetingProps {
    name: string; // type pour la prop name
}

// Définir le composant Greeting avec des types
const Greeting: React.FC<GreetingProps> = ({ name }) => {
    return <div>Hello, {name}!</div>; // Rendu du composant
};

export default Greeting; // Exporter le composant par défaut
Code 02 : Composant Counter
typescript
Copier le code
import React, { Component } from 'react';

// Définir une interface pour l'état
interface CounterState {
    count: number; // type pour la propriété count
}

// Définir la classe Counter
class Counter extends Component<{}, CounterState> {
    // Initialiser l'état dans le constructeur
    state: CounterState = {
        count: 0, // Valeur initiale
    };

    // Méthode pour incrémenter le compteur
    increment = () => {
        this.setState({ count: this.state.count + 1 }); // Mise à jour de l'état
    };

    render() {
        return (
            <div>
                <p>Count: {this.state.count}</p>
                <button onClick={this.increment}>Increment</button> {/* Bouton pour incrémenter */}
            </div>
        );
    }
}

export default Counter; // Exporter le composant par défaut
Résumé des Changements
Ajout d'interfaces : Pour mieux typer les props et l'état, j'ai créé des interfaces GreetingProps et CounterState.
Types React.FC : J'ai utilisé React.FC pour définir le type du composant fonctionnel.
Syntaxe : J'ai corrigé des erreurs de syntaxe (comme les points-virgules inutiles) pour que le code soit valide.
