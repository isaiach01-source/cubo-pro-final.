import './style.css';
import { RubiksCubeElement } from '@houstonp/rubiks-cube/view';

RubiksCubeElement.register();

const mainApp = document.getElementById('main-app');
const learnPage = document.getElementById('learn-page');
const detailPage = document.getElementById('detail-page');
const navHome = document.getElementById('nav-home');
const navLearn = document.getElementById('nav-learn');

navHome.addEventListener('click', () => {
    mainApp.style.display = 'flex'; learnPage.style.display = 'none'; detailPage.style.display = 'none';
    navHome.classList.add('active'); navLearn.classList.remove('active');
});

navLearn.addEventListener('click', () => {
    mainApp.style.display = 'none'; learnPage.style.display = 'flex'; detailPage.style.display = 'none';
    navLearn.classList.add('active'); navHome.classList.remove('active');
    renderAlgoGrid();
});

const algorithmsDB = [
    // --- F2L (41 Casos) ---
    { id: 'f2l-1', type: 'F2L', name: 'F2L 1', setup: "R U R'", alg: "R U R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-2', type: 'F2L', name: 'F2L 2', setup: "F' U' F", alg: "F' U' F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-3', type: 'F2L', name: 'F2L 3', setup: "U' R U R'", alg: "U' R U R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-4', type: 'F2L', name: 'F2L 4', setup: "U R U' R'", alg: "U R U' R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-5', type: 'F2L', name: 'F2L 5', setup: "R U' R' U R U' R'", alg: "R U' R' U R U' R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-6', type: 'F2L', name: 'F2L 6', setup: "F' U F U' F' U F", alg: "F' U F U' F' U F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-7', type: 'F2L', name: 'F2L 7', setup: "U' R U2 R' U R U' R'", alg: "U' R U2 R' U R U' R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-8', type: 'F2L', name: 'F2L 8', setup: "U F' U2 F U' F' U F", alg: "U F' U2 F U' F' U F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-9', type: 'F2L', name: 'F2L 9', setup: "R U R' U' R U R'", alg: "R U R' U' R U R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-10', type: 'F2L', name: 'F2L 10', setup: "F' U' F U F' U' F", alg: "F' U' F U F' U' F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-11', type: 'F2L', name: 'F2L 11', setup: "U' R U' R' U R U' R'", alg: "U' R U' R' U R U' R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-12', type: 'F2L', name: 'F2L 12', setup: "U F' U F U' F' U F", alg: "U F' U F U' F' U F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-13', type: 'F2L', name: 'F2L 13', setup: "U' R U2 R' U' R U R'", alg: "U' R U2 R' U' R U R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-14', type: 'F2L', name: 'F2L 14', setup: "U F' U2 F U F' U' F", alg: "U F' U2 F U F' U' F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-15', type: 'F2L', name: 'F2L 15', setup: "R U2 R' U' R U R'", alg: "R U2 R' U' R U R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-16', type: 'F2L', name: 'F2L 16', setup: "F' U2 F U F' U' F", alg: "F' U2 F U F' U' F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-17', type: 'F2L', name: 'F2L 17', setup: "R U' R' U2 R U' R'", alg: "R U' R' U2 R U' R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-18', type: 'F2L', name: 'F2L 18', setup: "F' U F U2 F' U F", alg: "F' U F U2 F' U F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-19', type: 'F2L', name: 'F2L 19', setup: "R U' R' U R U' R'", alg: "R U' R' U R U' R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-20', type: 'F2L', name: 'F2L 20', setup: "F' U F U' F' U F", alg: "F' U F U' F' U F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-21', type: 'F2L', name: 'F2L 21', setup: "U R U' R' U R U' R'", alg: "U R U' R' U R U' R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-22', type: 'F2L', name: 'F2L 22', setup: "U' F' U F U' F' U F", alg: "U' F' U F U' F' U F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-23', type: 'F2L', name: 'F2L 23', setup: "R U R' U2 R U R'", alg: "R U R' U2 R U R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-24', type: 'F2L', name: 'F2L 24', setup: "F' U' F U2 F' U' F", alg: "F' U' F U2 F' U' F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-25', type: 'F2L', name: 'F2L 25', setup: "R U' R' U' R U R'", alg: "R U' R' U' R U R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-26', type: 'F2L', name: 'F2L 26', setup: "F' U F U F' U' F", alg: "F' U F U F' U' F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-27', type: 'F2L', name: 'F2L 27', setup: "R U2 R' U R U' R'", alg: "R U2 R' U R U' R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-28', type: 'F2L', name: 'F2L 28', setup: "F' U2 F U' F' U F", alg: "F' U2 F U' F' U F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-29', type: 'F2L', name: 'F2L 29', setup: "R U R' U' R U' R'", alg: "R U R' U' R U' R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-30', type: 'F2L', name: 'F2L 30', setup: "F' U' F U F' U F", alg: "F' U' F U F' U F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-31', type: 'F2L', name: 'F2L 31', setup: "U' R U' R' U2 R U' R'", alg: "U' R U' R' U2 R U' R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-32', type: 'F2L', name: 'F2L 32', setup: "U F' U F U2 F' U F", alg: "U F' U F U2 F' U F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-33', type: 'F2L', name: 'F2L 33', setup: "U' R U R' U' R U R'", alg: "U' R U R' U' R U R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-34', type: 'F2L', name: 'F2L 34', setup: "U F' U' F U F' U' F", alg: "U F' U' F U F' U' F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-35', type: 'F2L', name: 'F2L 35', setup: "R U R' U2 R U' R'", alg: "R U R' U2 R U' R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-36', type: 'F2L', name: 'F2L 36', setup: "F' U' F U2 F' U F", alg: "F' U' F U2 F' U F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-37', type: 'F2L', name: 'F2L 37', setup: "R U' R' U' R U' R'", alg: "R U' R' U' R U' R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-38', type: 'F2L', name: 'F2L 38', setup: "F' U F U F' U F", alg: "F' U F U F' U F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-39', type: 'F2L', name: 'F2L 39', setup: "R U R' U' R U2 R'", alg: "R U R' U' R U2 R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-40', type: 'F2L', name: 'F2L 40', setup: "F' U' F U F' U2 F", alg: "F' U' F U F' U2 F", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },
    { id: 'f2l-41', type: 'F2L', name: 'F2L 41', setup: "R U' R' U R U2 R'", alg: "R U' R' U R U2 R'", status: 'unstarted', diagram: ['g','g','g','g','y','g','g','g','g'] },

    // --- OLL (57 Casos) ---
    { id: 'oll-1', type: 'OLL', name: 'OLL 1 (Punto)', setup: "R U2 R2 F R F' U2 R' F R F'", alg: "R U2 R2 F R F' U2 R' F R F'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-2', type: 'OLL', name: 'OLL 2 (Punto)', setup: "r U r' U2 r U2 R' U2 R U' r'", alg: "r U r' U2 r U2 R' U2 R U' r'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-3', type: 'OLL', name: 'OLL 3 (Punto)', setup: "r' R2 U R' U r U2 r' U R' M'", alg: "r' R2 U R' U r U2 r' U R' M'", status: 'unstarted', diagram: ['y','y','g','y','y','y','g','y','y'] },
    { id: 'oll-4', type: 'OLL', name: 'OLL 4 (Punto)', setup: "r U2 R' U' R U' r'", alg: "r U2 R' U' R U' r'", status: 'unstarted', diagram: ['y','g','y','g','y','g','y','g','y'] },
    { id: 'oll-5', type: 'OLL', name: 'OLL 5 (Cuadrado)', setup: "r' U' R U' R' U2 r", alg: "r' U' R U' R' U2 r", status: 'unstarted', diagram: ['y','g','y','g','y','g','y','g','y'] },
    { id: 'oll-6', type: 'OLL', name: 'OLL 6 (Cuadrado)', setup: "r U R' U R U2 r'", alg: "r U R' U R U2 r'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-7', type: 'OLL', name: 'OLL 7 (Cruz)', setup: "r U2 R' U' R U' r'", alg: "r U2 R' U' R U' r'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-8', type: 'OLL', name: 'OLL 8 (Cruz)', setup: "r' U2 R U R' U r", alg: "r' U2 R U R' U r", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-9', type: 'OLL', name: 'OLL 9 (Pez)', setup: "R U R' U' R' F R2 U R' U' F'", alg: "R U R' U' R' F R2 U R' U' F'", status: 'unstarted', diagram: ['y','g','y','y','y','g','g','y','g'] },
    { id: 'oll-10', type: 'OLL', name: 'OLL 10 (Pez)', setup: "R U R' U R' F R F' R U2 R'", alg: "R U R' U R' F R F' R U2 R'", status: 'unstarted', diagram: ['y','g','y','y','y','g','g','y','g'] },
    { id: 'oll-11', type: 'OLL', name: 'OLL 11 (Pez)', setup: "r U R' U R' F R F' R U2 r'", alg: "r U R' U R' F R F' R U2 r'", status: 'unstarted', diagram: ['g','y','g','y','y','y','y','g','y'] },
    { id: 'oll-12', type: 'OLL', name: 'OLL 12 (Pez)', setup: "F R U R' U' F' U F R U R' U' F'", alg: "F R U R' U' F' U F R U R' U' F'", status: 'unstarted', diagram: ['g','y','g','y','y','y','y','g','y'] },
    { id: 'oll-13', type: 'OLL', name: 'OLL 13 (Cruz)', setup: "F U R U' R2 F' R U R U' R'", alg: "F U R U' R2 F' R U R U' R'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-14', type: 'OLL', name: 'OLL 14 (Cruz)', setup: "R' F R U R' F' R F U' F'", alg: "R' F R U R' F' R F U' F'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-15', type: 'OLL', name: 'OLL 15 (Cruz)', setup: "r' U' r R' U' R U r' U r", alg: "r' U' r R' U' R U r' U r", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-16', type: 'OLL', name: 'OLL 16 (Cruz)', setup: "r U r' R U R' U' r U' r'", alg: "r U r' R U R' U' r U' r'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-17', type: 'OLL', name: 'OLL 17 (Punto)', setup: "F R' F' R U2 F R' F' R U' R U' R'", alg: "F R' F' R U2 F R' F' R U' R U' R'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-18', type: 'OLL', name: 'OLL 18 (Punto)', setup: "r' U2 R U R' U r2 U2 R' U' R U' r'", alg: "r' U2 R U R' U r2 U2 R' U' R U' r'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-19', type: 'OLL', name: 'OLL 19 (Punto)', setup: "F R' F' R M U R U' R' U' M'", alg: "F R' F' R M U R U' R' U' M'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-20', type: 'OLL', name: 'OLL 20 (Punto)', setup: "r U R' U' M2 U R U' R' U' M'", alg: "r U R' U' M2 U R U' R' U' M'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-21', type: 'OLL', name: 'OLL 21 (Cruz)', setup: "R U R' U R U' R' U R U2 R'", alg: "R U R' U R U' R' U R U2 R'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-22', type: 'OLL', name: 'OLL 22 (Cruz)', setup: "R' U2 R2 U R2 U R2 U2 R'", alg: "R' U2 R2 U R2 U R2 U2 R'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-23', type: 'OLL', name: 'OLL 23 (Cruz)', setup: "R U2 R D R' U2 R D' R2", alg: "R U2 R D R' U2 R D' R2", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-24', type: 'OLL', name: 'OLL 24 (Cruz)', setup: "F R' F' r U R U' r'", alg: "F R' F' r U R U' r'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-25', type: 'OLL', name: 'OLL 25 (Cruz)', setup: "R' F' r U R U' r' F", alg: "R' F' r U R U' r' F", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-26', type: 'OLL', name: 'OLL 26 (Pez)', setup: "R U R' U R U2 R'", alg: "R U R' U R U2 R'", status: 'unstarted', diagram: ['y','g','y','y','y','g','g','y','g'] },
    { id: 'oll-27', type: 'OLL', name: 'OLL 27 (Pez)', setup: "R U2 R' U' R U' R'", alg: "R U2 R' U' R U' R'", status: 'unstarted', diagram: ['y','g','y','y','y','g','g','y','g'] },
    { id: 'oll-28', type: 'OLL', name: 'OLL 28 (Cruz)', setup: "R U R' U' M' U R U' r'", alg: "R U R' U' M' U R U' r'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-29', type: 'OLL', name: 'OLL 29 (Cruz)', setup: "M F R' F' R U R U' R' U' M'", alg: "M F R' F' R U R U' R' U' M'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-30', type: 'OLL', name: 'OLL 30 (Cruz)', setup: "F U R U2 R' U R U2 R' U' F'", alg: "F U R U2 R' U R U2 R' U' F'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-31', type: 'OLL', name: 'OLL 31 (Punto)', setup: "R' F R U R' U' F' U R", alg: "R' F R U R' U' F' U R", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-32', type: 'OLL', name: 'OLL 32 (Punto)', setup: "R' F R U f R' F' R U R U' R' S'", alg: "R' F R U f R' F' R U R U' R' S'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-33', type: 'OLL', name: 'OLL 33 (Punto)', setup: "F R' F' R U R U' R'", alg: "F R' F' R U R U' R'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-34', type: 'OLL', name: 'OLL 34 (Punto)', setup: "F U R' U' R' F' R U R2 U' R'", alg: "F U R' U' R' F' R U R2 U' R'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-35', type: 'OLL', name: 'OLL 35 (Punto)', setup: "R U2 R' F R' F' R2 U2 R'", alg: "R U2 R' F R' F' R2 U2 R'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-36', type: 'OLL', name: 'OLL 36 (Cruz)', setup: "R' U' R U' R' U R U' R' U2 R", alg: "R' U' R U' R' U R U' R' U2 R", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-37', type: 'OLL', name: 'OLL 37 (Cruz)', setup: "F R' F' R U R U' R'", alg: "F R' F' R U R U' R'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-38', type: 'OLL', name: 'OLL 38 (Cruz)', setup: "R U R' U R U' R' U' R' F R F'", alg: "R U R' U R U' R' U' R' F R F'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-39', type: 'OLL', name: 'OLL 39 (Cruz)', setup: "L F' L' U' L U F U' L'", alg: "L F' L' U' L U F U' L'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-40', type: 'OLL', name: 'OLL 40 (Cruz)', setup: "R' F R U R' U' F' U R", alg: "R' F R U R' U' F' U R", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-41', type: 'OLL', name: 'OLL 41 (Punto)', setup: "R U R' U R U2 R' F R U R' U' F'", alg: "R U R' U R U2 R' F R U R' U' F'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-42', type: 'OLL', name: 'OLL 42 (Punto)', setup: "R' U' R U' R' U2 R F R U R' U' F'", alg: "R' U' R U' R' U2 R F R U R' U' F'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'oll-43', type: 'OLL', name: 'OLL 43 (Cruz)', setup: "F' U' L' U L F", alg: "F' U' L' U L F", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-44', type: 'OLL', name: 'OLL 44 (Cruz)', setup: "F U R U' R' F'", alg: "F U R U' R' F'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-45', type: 'OLL', name: 'OLL 45 (Cruz)', setup: "F R U R' U' F'", alg: "F R U R' U' F'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-46', type: 'OLL', name: 'OLL 46 (Cruz)', setup: "R' U' R' F R F' U R", alg: "R' U' R' F R F' U R", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-47', type: 'OLL', name: 'OLL 47 (Cruz)', setup: "R' U' R' F R F' R' F R F' U R", alg: "R' U' R' F R F' R' F R F' U R", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-48', type: 'OLL', name: 'OLL 48 (Cruz)', setup: "F R U R' U' R U R' U' F'", alg: "F R U R' U' R U R' U' F'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-49', type: 'OLL', name: 'OLL 49 (Cruz)', setup: "r U' r2 U r2 U r2 U' r", alg: "r U' r2 U r2 U r2 U' r", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-50', type: 'OLL', name: 'OLL 50 (Cruz)', setup: "r' U r2 U' r2 U' r2 U r'", alg: "r' U r2 U' r2 U' r2 U r'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-51', type: 'OLL', name: 'OLL 51 (Cruz)', setup: "F U R U' R' U R U' R' F'", alg: "F U R U' R' U R U' R' F'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-52', type: 'OLL', name: 'OLL 52 (Cruz)', setup: "R U R' U R U' B U' B' R'", alg: "R U R' U R U' B U' B' R'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-53', type: 'OLL', name: 'OLL 53 (Cruz)', setup: "r' U' R U' R' U R U' R' U2 r", alg: "r' U' R U' R' U R U' R' U2 r", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-54', type: 'OLL', name: 'OLL 54 (Cruz)', setup: "r U R' U R U' R' U R U2 r'", alg: "r U R' U R U' R' U R U2 r'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-55', type: 'OLL', name: 'OLL 55 (Cruz)', setup: "R' F R U R U' R2 F' R2 U' R' U R U R'", alg: "R' F R U R U' R2 F' R2 U' R' U R U R'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-56', type: 'OLL', name: 'OLL 56 (Cruz)', setup: "r' U' r U' R' U R U' R' U R r' U r", alg: "r' U' r U' R' U R U' R' U R r' U r", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'oll-57', type: 'OLL', name: 'OLL 57 (Cruz)', setup: "R U R' U' M' U R U' r'", alg: "R U R' U' M' U R U' r'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },

    // --- PLL (21 Casos) ---
    { id: 'pll-1', type: 'PLL', name: 'PLL Aa', setup: "x R' U R' D2 R U' R' D2 R2 x'", alg: "x R' U R' D2 R U' R' D2 R2 x'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'pll-2', type: 'PLL', name: 'PLL Ab', setup: "x R2 D2 R U R' D2 R U' R x'", alg: "x R2 D2 R U R' D2 R U' R x'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'pll-3', type: 'PLL', name: 'PLL E', setup: "x' R U' R' D R U R' D' R U R' D R U' R' D' x", alg: "x' R U' R' D R U R' D' R U R' D R U' R' D' x", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'pll-4', type: 'PLL', name: 'PLL F', setup: "R' U' F' R U R' U' R' F R2 U' R' U' R U R' U R", alg: "R' U' F' R U R' U' R' F R2 U' R' U' R U R' U R", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'pll-5', type: 'PLL', name: 'PLL Ga', setup: "R2 U R' U R' U' R U' R2 U' D R' U R D'", alg: "R2 U R' U R' U' R U' R2 U' D R' U R D'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'pll-6', type: 'PLL', name: 'PLL Gb', setup: "R' U' R U D' R2 U R' U R U' R U' R2 D", alg: "R' U' R U D' R2 U R' U R U' R U' R2 D", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'pll-7', type: 'PLL', name: 'PLL Gc', setup: "R2 U' R U' R U R' U R2 U D' R U' R' D", alg: "R2 U' R U' R U R' U R2 U D' R U' R' D", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'pll-8', type: 'PLL', name: 'PLL Gd', setup: "R U R' U' D R2 U' R U' R' U R' U R2 D'", alg: "R U R' U' D R2 U' R U' R' U R' U R2 D'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'pll-9', type: 'PLL', name: 'PLL H', setup: "M2 U M2 U2 M2 U M2", alg: "M2 U M2 U2 M2 U M2", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'pll-10', type: 'PLL', name: 'PLL Ja', setup: "L' U' L F L' U' L U L F' L2 U L U", alg: "L' U' L F L' U' L U L F' L2 U L U", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'pll-11', type: 'PLL', name: 'PLL Jb', setup: "R U R' F' R U R' U' R' F R2 U' R'", alg: "R U R' F' R U R' U' R' F R2 U' R'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'pll-12', type: 'PLL', name: 'PLL Na', setup: "R U R' U R U R' F' R U R' U' R' F R2 U' R' U2 R U' R'", alg: "R U R' U R U R' F' R U R' U' R' F R2 U' R' U2 R U' R'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'pll-13', type: 'PLL', name: 'PLL Nb', setup: "R' U R U' R' F' U' F R U R' F R' F' R U' R", alg: "R' U R U' R' F' U' F R U R' F R' F' R U' R", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'pll-14', type: 'PLL', name: 'PLL Ra', setup: "R U' R' U' R U R D R' U' R D' R' U2 R'", alg: "R U' R' U' R U R D R' U' R D' R' U2 R'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'pll-15', type: 'PLL', name: 'PLL Rb', setup: "R' U2 R U2 R' F R U R' U' R' F' R2", alg: "R' U2 R U2 R' F R U R' U' R' F' R2", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'pll-16', type: 'PLL', name: 'PLL T', setup: "R U R' U' R' F R2 U' R' U' R U R' F'", alg: "R U R' U' R' F R2 U' R' U' R U R' F'", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'pll-17', type: 'PLL', name: 'PLL Ua', setup: "M2 U M U2 M' U M2", alg: "M2 U M U2 M' U M2", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'pll-18', type: 'PLL', name: 'PLL Ub', setup: "M2 U' M U2 M' U' M2", alg: "M2 U' M U2 M' U' M2", status: 'unstarted', diagram: ['y','y','y','g','y','g','g','g','g'] },
    { id: 'pll-19', type: 'PLL', name: 'PLL V', setup: "R' U R' U' y R' F' R2 U' R' U R' F R F", alg: "R' U R' U' y R' F' R2 U' R' U R' F R F", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'pll-20', type: 'PLL', name: 'PLL Y', setup: "F R U' R' U' R U R' F' R U R' U' R' F R F'", alg: "F R U' R' U' R U R' F' R U R' U' R' F R F'", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] },
    { id: 'pll-21', type: 'PLL', name: 'PLL Z', setup: "M' U M2 U M2 U M' U2 M2", alg: "M' U M2 U M2 U M' U2 M2", status: 'unstarted', diagram: ['g','y','g','y','y','y','g','y','g'] }
];

let currentAlgoType = 'OLL';
let currentAlgo = null;
let learnCube = null;
let currentMoves = [];
let currentMoveIndex = 0;
let playbackSpeed = 1;

algorithmsDB.forEach(algo => {
    const savedStatus = localStorage.getItem(`algo_status_${algo.id}`);
    if (savedStatus) algo.status = savedStatus;
});

document.querySelectorAll('.algo-tab').forEach(tab => {
    tab.addEventListener('click', (e) => {
        document.querySelectorAll('.algo-tab').forEach(t => t.classList.remove('active'));
        e.target.classList.add('active');
        currentAlgoType = e.target.getAttribute('data-type');
        renderAlgoGrid();
    });
});

function renderAlgoGrid() {
    const grid = document.getElementById('algo-grid'); grid.innerHTML = '';
    const filteredAlgos = algorithmsDB.filter(a => a.type === currentAlgoType);
    
    filteredAlgos.forEach(algo => {
        const card = document.createElement('div'); card.className = 'algo-card';
        
        let diagramHTML = '<div class="cube-3d-wrapper"><div class="cube-2d">';
        algo.diagram.forEach(color => { diagramHTML += `<div class="sticker ${color}"></div>`; });
        diagramHTML += '</div></div>';
        
        card.innerHTML = `
            ${diagramHTML}
            <h3>${algo.name}</h3>
            <small style="color: ${algo.status === 'learned' ? '#10b981' : algo.status === 'learning' ? '#f59e0b' : '#94a3b8'}">
                ${algo.status === 'learned' ? '✅ Aprendido' : algo.status === 'learning' ? '⏳ Aprendiendo' : '⚪ Sin empezar'}
            </small>`;
        card.addEventListener('click', () => openDetail(algo));
        grid.appendChild(card);
    });
}

function openDetail(algo) {
    currentAlgo = algo; learnPage.style.display = 'none'; detailPage.style.display = 'flex';
    document.getElementById('detail-title').textContent = algo.name;
    document.getElementById('algo-string').textContent = algo.alg;
    
    document.querySelectorAll('.btn-status').forEach(btn => {
        btn.classList.remove('active');
        if(btn.getAttribute('data-status') === algo.status) btn.classList.add('active');
    });

    const cubeContainer = document.getElementById('detail-cube-area');
    cubeContainer.innerHTML = ''; 
    
    const newCube = document.createElement('rubiks-cube');
    newCube.id = 'learn-cube';
    newCube.setAttribute('cube-type', 'Three');
    newCube.setAttribute('animation-speed-ms', 300 / playbackSpeed);
    cubeContainer.appendChild(newCube);
    
    learnCube = newCube;
    currentMoves = algo.alg.split(' ');
    currentMoveIndex = 0;

    setTimeout(async () => {
        await learnCube.reset(); 
        await applyMovesToCube(learnCube, algo.setup);
    }, 150);
}

document.getElementById('back-to-learn').addEventListener('click', () => {
    detailPage.style.display = 'none'; learnPage.style.display = 'flex'; renderAlgoGrid();
});

document.getElementById('btn-play').addEventListener('click', async () => {
    if (!learnCube || !currentAlgo) return;
    await learnCube.reset(); 
    await applyMovesToCube(learnCube, currentAlgo.setup);
    await new Promise(r => setTimeout(r, 500)); 
    
    currentMoveIndex = 0;
    for (let i = 0; i < currentMoves.length; i++) {
        await learnCube.move(currentMoves[i]);
        currentMoveIndex++;
    }
});

document.getElementById('btn-next-move').addEventListener('click', async () => {
    if (currentMoveIndex < currentMoves.length) {
        await learnCube.move(currentMoves[currentMoveIndex]);
        currentMoveIndex++;
    }
});

document.getElementById('btn-prev-move').addEventListener('click', async () => {
    if (currentMoveIndex > 0) {
        currentMoveIndex--;
        await learnCube.reset();
        await applyMovesToCube(learnCube, currentAlgo.setup);
        for (let i = 0; i < currentMoveIndex; i++) {
            await learnCube.move(currentMoves[i]);
        }
    }
});

document.querySelectorAll('.speed-btn').forEach(btn => {
    btn.addEventListener('click', (e) => {
        document.querySelectorAll('.speed-btn').forEach(b => b.classList.remove('active'));
        e.target.classList.add('active');
        playbackSpeed = parseFloat(e.target.getAttribute('data-speed'));
        if (learnCube) learnCube.setAttribute('animation-speed-ms', 300 / playbackSpeed);
    });
});

document.querySelectorAll('.btn-status').forEach(btn => {
    btn.addEventListener('click', () => {
        if (!currentAlgo) return;
        currentAlgo.status = btn.getAttribute('data-status');
        localStorage.setItem(`algo_status_${currentAlgo.id}`, currentAlgo.status);
        document.querySelectorAll('.btn-status').forEach(b => b.classList.remove('active'));
        btn.classList.add('active');
    });
});

async function applyMovesToCube(cubeElement, movesString) {
    for (const move of movesString.split(' ')) { if (move.trim() !== '') await cubeElement.move(move); }
}

// LÓGICA DEL TEMPORIZADOR
const appContainer = document.getElementById('app-container');
const cube = document.getElementById('cube');
const cubeArea = document.getElementById('cube-area');
const timerEl = document.getElementById('timer');
const timerContainer = document.getElementById('timer-container');
const statusEl = document.getElementById('status');
const penaltyMenu = document.getElementById('penalty-menu');
const moveCountEl = document.getElementById('move-count');
const moveCounterCont = document.getElementById('move-counter');
const virtualControls = document.getElementById('virtual-controls');
const tabVirtual = document.getElementById('tab-virtual');
const tabPhysical = document.getElementById('tab-physical');
const btnNewScramble = document.getElementById('new-scramble');
const btnRepeatScramble = document.getElementById('repeat-scramble');
const btnExportCsv = document.getElementById('export-csv');
const btnClearHistory = document.getElementById('clear-history');
const speedSlider = document.getElementById('speed-slider');
const speedValue = document.getElementById('speed-value');
const ao5El = document.getElementById('ao5');
const ao12El = document.getElementById('ao12');
const historyListEl = document.getElementById('history-list');

let currentMode = 'virtual'; let state = 'IDLE'; let inspectionInterval = null;
let inspectionTimeLeft = 15.0; let solveInterval = null; let solveTime = 0;
let moveCount = 0; let currentScramble = '';
let history = JSON.parse(localStorage.getItem('rubikHistory')) || [];
let lastRecordIndex = -1; let holdTimer = null; let isHolding = false;

const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
function playClickSound(freq = 800) {
    if (audioCtx.state === 'suspended') audioCtx.resume();
    const osc = audioCtx.createOscillator(); const gain = audioCtx.createGain();
    osc.type = 'sine'; osc.frequency.setValueAtTime(freq, audioCtx.currentTime);
    gain.gain.setValueAtTime(0.1, audioCtx.currentTime);
    gain.gain.exponentialRampToValueAtTime(0.01, audioCtx.currentTime + 0.05);
    osc.connect(gain); gain.connect(audioCtx.destination); osc.start(); osc.stop(audioCtx.currentTime + 0.05);
}

speedSlider.addEventListener('input', (e) => {
    cube.setAttribute('animation-speed-ms', e.target.value);
    speedValue.textContent = (e.target.value / 1000).toFixed(1) + 's';
});

function cambiarModo(modo) {
    currentMode = modo; cubeArea.classList.remove('hidden');
    if (modo === 'virtual') {
        tabVirtual.classList.add('active'); tabPhysical.classList.remove('active');
        cube.style.display = 'block'; virtualControls.style.display = 'block'; moveCounterCont.style.display = 'none';
        appContainer.classList.remove('physical-active');
    } else {
        tabPhysical.classList.add('active'); tabVirtual.classList.remove('active');
        cube.style.display = 'block'; virtualControls.style.display = 'none'; moveCounterCont.style.display = 'none';
        appContainer.classList.add('physical-active');
    }
    resetState();
}
tabVirtual.addEventListener('click', () => cambiarModo('virtual'));
tabPhysical.addEventListener('click', () => cambiarModo('physical'));

function generateScramble(length = 15) {
    const faces = ['R', 'L', 'U', 'D', 'F', 'B']; const modifiers = ['', "'", '2'];
    let scramble = []; let lastFace = '';
    for (let i = 0; i < length; i++) {
        let face; do { face = faces[Math.floor(Math.random() * faces.length)]; } while (face === lastFace); 
        lastFace = face; scramble.push(face + modifiers[Math.floor(Math.random() * modifiers.length)]);
    }
    return scramble.join(' ');
}

async function applyScramble(moves) {
    for (const move of moves.split(' ')) { if (move.trim() !== '') await cube.move(move); }
}

btnNewScramble.addEventListener('click', async () => {
    cubeArea.classList.remove('hidden'); await cube.reset();
    currentScramble = generateScramble(15); statusEl.textContent = `Scramble: ${currentScramble}`;
    resetState(); btnRepeatScramble.disabled = false; state = 'IS_SCRAMBLING';
    await applyScramble(currentScramble);
    if (state === 'IS_SCRAMBLING' && currentMode === 'physical') {
        cubeArea.classList.add('hidden'); iniciarInspeccion();
    } else if (state === 'IS_SCRAMBLING') { state = 'IDLE'; }
});

btnRepeatScramble.addEventListener('click', async () => {
    if (!currentScramble) return; cubeArea.classList.remove('hidden'); await cube.reset();
    statusEl.textContent = `Scramble: ${currentScramble}`; resetState(); state = 'IS_SCRAMBLING';
    await applyScramble(currentScramble);
    if (state === 'IS_SCRAMBLING' && currentMode === 'physical') {
        cubeArea.classList.add('hidden'); iniciarInspeccion();
    } else if (state === 'IS_SCRAMBLING') { state = 'IDLE'; }
});

cubeArea.addEventListener('click', () => {
    if (state === 'IS_SCRAMBLING' && currentMode === 'physical') {
        state = 'IDLE'; cubeArea.classList.add('hidden'); iniciarInspeccion();
    }
});

async function hacerMovimiento(move) {
    if (currentMode !== 'virtual' || state === 'INSPECTING' || state === 'READY') return;
    playClickSound(600);
    if (state === 'SOLVING') { moveCount++; moveCountEl.textContent = moveCount; }
    await cube.move(move);
}

document.querySelectorAll('.move-btn').forEach(btn => {
    btn.addEventListener('click', () => hacerMovimiento(btn.getAttribute('data-move')));
});

document.addEventListener('keydown', (e) => {
    if (currentMode === 'virtual' && state !== 'INSPECTING' && state !== 'READY') {
        const key = e.key.toUpperCase();
        if (['U', 'D', 'L', 'R', 'F', 'B'].includes(key)) hacerMovimiento(e.shiftKey ? key + "'" : key);
    }
});

timerContainer.addEventListener('pointerdown', (e) => {
    e.preventDefault(); if (penaltyMenu.classList.contains('show')) return;
    isHolding = false;
    if (state === 'IDLE' || state === 'FINISHED') {
        holdTimer = setTimeout(() => { isHolding = true; if (state === 'FINISHED') { penaltyMenu.classList.add('show'); playClickSound(400); } }, 500);
    }
    if (state === 'INSPECTING' || state === 'IDLE') {
        if (state === 'INSPECTING') { state = 'READY'; timerContainer.classList.add('ready'); }
    }
});

timerContainer.addEventListener('pointerup', (e) => {
    e.preventDefault(); clearTimeout(holdTimer);
    if (isHolding) { isHolding = false; return; }
    if (state === 'READY') { timerContainer.classList.remove('ready'); iniciarCronometro(); } 
    else if (state === 'IDLE' || state === 'FINISHED') { iniciarInspeccion(); } 
    else if (state === 'SOLVING') { detenerCronometro(false); }
});

timerContainer.addEventListener('pointerleave', () => {
    if (state === 'READY') { state = 'INSPECTING'; timerContainer.classList.remove('ready'); }
    clearTimeout(holdTimer); isHolding = false;
});

function iniciarInspeccion() {
    if (state === 'SOLVING') return; resetState(); state = 'INSPECTING'; inspectionTimeLeft = 15.0;
    timerEl.textContent = `${inspectionTimeLeft.toFixed(1)}s`; timerEl.style.color = "#fbbf24";
    statusEl.textContent = "Inspección... (Mantén presionado para arrancar)";
    inspectionInterval = setInterval(() => {
        inspectionTimeLeft -= 0.1;
        if (inspectionTimeLeft <= 0) {
            clearInterval(inspectionInterval); timerEl.textContent = "+2"; timerEl.style.color = "#ef4444"; statusEl.textContent = "¡Excedido! (+2s)";
        } else { timerEl.textContent = `${inspectionTimeLeft.toFixed(1)}s`; }
    }, 100);
}

function iniciarCronometro() {
    state = 'SOLVING'; clearInterval(inspectionInterval); solveTime = 0; moveCount = 0; moveCountEl.textContent = moveCount;
    timerContainer.classList.add('solving'); statusEl.textContent = "¡Resolviendo!"; timerEl.textContent = "0.00s"; timerEl.style.color = "#10b981";
    if (currentMode === 'virtual') moveCounterCont.style.display = 'block';
    solveInterval = setInterval(() => { solveTime += 0.01; timerEl.textContent = `${solveTime.toFixed(2)}s`; }, 10);
}

function detenerCronometro(isAutoDetected = false) {
    if (state !== 'SOLVING') return; state = 'FINISHED'; clearInterval(solveInterval); timerContainer.classList.remove('solving'); timerEl.style.color = "#fbbf24";
    let finalTime = solveTime;
    if (timerEl.textContent === "+2" || inspectionTimeLeft <= 0) {
        finalTime += 2; statusEl.textContent = `Tiempo: ${finalTime.toFixed(2)}s (+2 penalización)`;
    } else if (isAutoDetected) { statusEl.textContent = `🎉 ¡Cruz resuelta en ${finalTime.toFixed(2)}s!`; } 
    else { statusEl.textContent = `¡Tiempo: ${finalTime.toFixed(2)}s!`; }
    timerEl.textContent = `${finalTime.toFixed(2)}s`;
    guardarEnHistorial(finalTime, currentMode === 'virtual' ? moveCount : '-', 'OK');
}

function resetState() {
    clearInterval(inspectionInterval); clearInterval(solveInterval);
    state = 'IDLE'; solveTime = 0; inspectionTimeLeft = 15.0;
    timerEl.textContent = `15.0s`; timerEl.style.color = "#fbbf24";
    timerContainer.classList.remove('ready', 'solving'); moveCounterCont.style.display = 'none'; penaltyMenu.classList.remove('show');
}

document.querySelectorAll('.penalty-btn').forEach(btn => {
    btn.addEventListener('click', (e) => {
        e.stopPropagation(); const penalty = btn.getAttribute('data-penalty'); aplicarPenalizacion(penalty); penaltyMenu.classList.remove('show');
    });
});

function aplicarPenalizacion(tipo) {
    if (lastRecordIndex < 0) return; let record = history[lastRecordIndex]; let timeText = `${record.baseTime.toFixed(2)}s`;
    if (tipo === 'DNF') { record.time = 9999; record.penalty = 'DNF'; timeText = "DNF"; } 
    else if (tipo === '+2') { record.time = record.baseTime + 2; record.penalty = '+2'; timeText = `${record.time.toFixed(2)}s (+2)`; } 
    else { record.time = record.baseTime; record.penalty = 'OK'; timeText = `${record.time.toFixed(2)}s`; }
    timerEl.textContent = timeText; localStorage.setItem('rubikHistory', JSON.stringify(history)); actualizarHistorialUI();
}

function guardarEnHistorial(time, moves, penalty) {
    const record = { baseTime: time, time: time, moves, penalty, date: new Date().toLocaleDateString() };
    history.push(record); lastRecordIndex = history.length - 1; localStorage.setItem('rubikHistory', JSON.stringify(history)); actualizarHistorialUI();
}

function actualizarHistorialUI() {
    historyListEl.innerHTML = ''; const recent = history.slice(-15).reverse();
    recent.forEach((r, i) => {
        const realIndex = history.length - 1 - i; const li = document.createElement('li');
        let t = r.time === 9999 ? 'DNF' : r.time.toFixed(2) + 's'; if (r.penalty === '+2') t += " (+2)";
        li.innerHTML = `<span>${t} <small style="color:#64748b">(${r.moves} movs)</small></span><button class="delete-btn" data-index="${realIndex}" title="Eliminar tiempo">✕</button>`;
        historyListEl.appendChild(li);
    });
    document.querySelectorAll('.delete-btn').forEach(btn => {
        btn.addEventListener('click', (e) => {
            const index = parseInt(e.target.getAttribute('data-index')); eliminarTiempo(index);
        });
    });
    ao5El.textContent = calcularPromedio(5); ao12El.textContent = calcularPromedio(12);
}

function eliminarTiempo(index) {
    history.splice(index, 1); localStorage.setItem('rubikHistory', JSON.stringify(history)); actualizarHistorialUI();
}

btnClearHistory.addEventListener('click', () => {
    if(confirm('¿Estás seguro de que quieres borrar todo el historial?')) {
        history = []; localStorage.removeItem('rubikHistory'); actualizarHistorialUI();
    }
});

function calcularPromedio(n) {
    if (history.length < n) return '-'; const subset = history.slice(-n).map(r => r.time);
    subset.sort((a, b) => a - b); if (subset[subset.length - 1] === 9999 && subset[subset.length - 2] === 9999) return 'DNF';
    const validTimes = subset.slice(1, n - 1); const sum = validTimes.reduce((a, b) => a + b, 0); return (sum / validTimes.length).toFixed(2) + 's';
}

btnExportCsv.addEventListener('click', () => {
    if (history.length === 0) return alert("No hay tiempos.");
    let csvContent = "data:text/csv;charset=utf-8,Fecha,Tiempo(s),Penalizacion,Movimientos\n";
    history.forEach(row => {
        let t = row.time === 9999 ? 'DNF' : row.time.toFixed(2); csvContent += `${row.date},${t},${row.penalty},${row.moves}\n`;
    });
    const link = document.createElement("a"); link.setAttribute("href", encodeURI(csvContent)); link.setAttribute("download", "tiempos_cubo.csv"); link.click();
});

cube.addEventListener('state', (event) => {
    if (state !== 'SOLVING' || currentMode !== 'virtual') return;
    try {
        const stateString = event.detail.state;
        const isWhiteFaceSolved = stateString.slice(0, 9) === 'UUUUUUUUU';
        const areEdgesAligned = 
            stateString[1] === 'U' && stateString[10] === 'R' && stateString[3] === 'U' && stateString[19] === 'F' &&
            stateString[5] === 'U' && stateString[37] === 'L' && stateString[7] === 'U' && stateString[46] === 'B';
        if (isWhiteFaceSolved && areEdgesAligned) { detenerCronometro(true); }
    } catch (e) {}
});

resetState();
actualizarHistorialUI();
