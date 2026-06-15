# __Experiencia y Conocimientos__

---

Soy estudiante de ciberseguridad con un fuerte interés en la administración de sistemas Linux, redes, automatización y seguridad ofensiva. Mi enfoque principal se centra en el aprendizaje práctico mediante laboratorios, desafíos técnicos y la construcción de proyectos personales que me permitan desarrollar una comprensión sólida de los fundamentos de la seguridad informática.

A lo largo de mi formación he trabajado con distribuciones Linux, scripting en Bash y herramientas utilizadas habitualmente en entornos de análisis y evaluación de seguridad. Considero que la mejor forma de aprender es mediante la práctica constante, por lo que dedico parte de mi tiempo al estudio de plataformas de entrenamiento, resolución de retos técnicos y documentación de conocimientos adquiridos.

Mis áreas de interés incluyen:

- __Sistemas Linux y administración básica.__
- __Redes y protocolos de comunicación.__
- __Bash Scripting y automatización de tareas.__
- __Seguridad ofensiva y pruebas de penetración.__
- __Enumeración y análisis de servicios.__
- __Metodologías de aprendizaje práctico en ciberseguridad.__

Actualmente continúo fortaleciendo mis conocimientos técnicos mediante el estudio diario, la resolución de laboratorios y el desarrollo de proyectos personales orientados a la seguridad informática. Mi objetivo es construir una base sólida que me permita contribuir profesionalmente al ecosistema de ciberseguridad en Latinoamérica y participar en iniciativas que promuevan el aprendizaje, la investigación y el uso responsable de la tecnología.

---
import { Image } from 'astro:assets';
import Layout from '../layouts/Layout.astro';
import { SITE_DATA } from '../constants';
import portraitImage from '../assets/portrait.png';
import '../styles/about.css';
---

<Layout pageTitle="Sobre Mi">
    <div class="page-container">

        <h1>Sobre mí</h1>

        <div class="about-content">

            <div class="about-intro-wrapper centered-column">

                <div class="about-header centered-column">
                    <Image 
                        src={portraitImage} 
                        alt={SITE_DATA.name} 
                        class="about-portrait" 
                    />
                    <h2 class="about-name">{SITE_DATA.name}</h2>