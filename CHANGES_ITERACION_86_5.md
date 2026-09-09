# PhysioSentinel Gait · Iteración 86.5

Hotfix de compatibilidad OpenCV/Streamlit Cloud.

- Se abandona OpenCV 4.13/4.14/5.0 para el runtime aislado por errores observados en `cv2.typing`, `mat_wrapper`, `dnn.DictValue` y cambios de API DNN.
- Primera opción: `opencv-contrib-python-headless==4.12.0.88`.
- Fallback automático e independiente: `opencv-contrib-python-headless==4.11.0.86`.
- Cada rueda se instala en un directorio `/tmp` distinto con `--no-deps`; nunca se mezclan dos distribuciones `cv2`.
- Se valida antes de continuar: `VideoCapture`, `aruco`, `dnn`, `DNN_BACKEND_OPENCV` y `DNN_TARGET_CPU`.
- RTMLib sigue configurado con backend `onnxruntime`; OpenCV-DNN sólo debe ser importable para la tabla de compatibilidad interna de RTMLib.
- Sin `packages.txt` y sin modificar/desinstalar paquetes del venv gestionado por Streamlit.
- No se modifican biomecánica, tracking, Supabase, HALPE26, reconstrucción 2D/3D, vídeos ni avatar anatómico V86.
