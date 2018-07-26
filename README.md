# Troubleshooting

Issues
 1. Anaconda spyder issue
    QOpenGLShaderProgram::uniformLocation(qt_Matrix): shader program is not linked
    QOpenGLShaderProgram: could not create shader program
    QOpenGLShader: could not create shader
    QOpenGLShader: could not create shader
    shader compilation failed:
    
Solution :
    Add the following lines to anaconda2/lib/python2.7/site-packages/spyder/app
    try:
        from OpenGL import GL
    except:
        pass

    import ctypes
    ctypes.CDLL("libGL.so.1", mode=ctypes.RTLD_GLOBAL)
