# Sistema de Navegación Autónoma en Interiores — Kobuki (TurtleBot2) + Kinect

Esta es una doocumentación técnica del sistema de navegación autónoma en interiores desarrollado durante una estadía profesional, usando un robot Kobuki (TurtleBot2) equipado con un sensor de profundidad Kinect Xbox 360, sobre ROS 2 Humble.

Este repositorio sirve como **guía/manual** para estudiantes o investigadores que deseen reproducir el sistema desde cero: desde la instalación del entorno hasta la navegación autónoma con SLAM.

## Demostración de SLAM y Navegación Autónoma.

<table>
  <tr>
    <td>
      <p align="center"><b>Video demostración Mapping</b></p>
      <a href="https://youtu.be/8vellvasD6s">
        <img src="https://youtube.com" alt="Demo SLAM 1" width="100%">
      </a>
    </td>
    <td>
      <p align="center"><b>Video demostración Navegación Autónoma</b></p>
      <a href="https://youtu.be/YxljkDkqRZY">
        <img src="https://youtube.com" alt="Demo SLAM 2" width="100%">
      </a>
    </td>
  </tr>
</table>


---

## Descripción del proyecto

El proyecto implementa un pipeline completo de navegación autónoma en interiores, desarrollado en siete etapas:

1. **Familiarización con el Kobuki** — control básico y verificación de comunicación
2. **Control de desplazamiento básico** — trayectorias controladas (líneas, giros)
3. **Integración de sensores** — Kinect Xbox 360 + conversión a LiDAR virtual
4. **Procesamiento de señales** — filtrado de ruido en `/scan`
5. **Implementación de SLAM** — mapeo con `slam_toolbox`
6. **Navegación autónoma en interiores** — Nav2 + AMCL + localización
7. **Validación y documentación** — pruebas en laboratorio y pasillo

## Hardware utilizado

| Componente | Detalle |
|---|---|
| Robot base | Kobuki (TurtleBot2) |
| Sensor de profundidad | Kinect Xbox 360 |
| Computadora de a bordo | Lenovo IdeaPad Slim 3 15IRH8 (Intel i7-13620H, Intel Iris Xe) |
| Alimentación del Kinect | Puerto de 12V 1.5A del Kobuki |

## Software utilizado

| Software | Versión |
|---|---|
| Sistema operativo | Ubuntu 22.04.5 LTS |
| Framework robótico | ROS 2 Humble |
| Middleware DDS | Cyclone DDS (`rmw_cyclonedds_cpp`) |
| SLAM | `slam_toolbox` |
| Navegación | `navigation2` (Nav2) |
| Localización | AMCL + `robot_localization` (EKF) |

---

## Estructura del repositorio

```
├── docs/                          # Guías paso a paso (seguir en orden)
│   ├── GUIA.pdf
├── src/                            # Paquetes ROS 2 propios (código fuente)
│   ├── kobuki_launch/
│   └── kobuki_trajectories/
└── Scripts_mapeo_&_navegacion/     # Scripts de arranque del robot para mapeo y navegación autonoma
    ├── arranque_mapeo.sh
    ├── arranque_navegacion.sh
```

> **Nota:** este repositorio solo incluye los paquetes desarrollados durante la estadía (`kobuki_launch`, `kobuki_trajectories`). Los paquetes de terceros (`kobuki_core`, `kobuki_ros`, `kinect_ros2`, `libfreenect`, `depthimage_to_laserscan`, `cmd_vel_mux`, `velocity_smoother`) **no se incluyen como código**; sus instrucciones de instalación están documentadas en [`docs/GUIA.pdf`](docs/GUIA.pdf).

---

## Inicio rápido

Para replicar el proyecto completo, sigue las guías en `docs/` en orden numérico:
Si algo falla en el camino, la misma guia reúne los problemas reales encontrados durante el desarrollo y sus soluciones verificadas.

---


Estudiante: Christopher Jared Villa Alanis

Proyecto desarrollado como parte de una estadía profesional universitaria.

Repositorio: [SLAM_Documentacion] (https://github.com/rocketant124/ros2-kinect-slam-navigation)
