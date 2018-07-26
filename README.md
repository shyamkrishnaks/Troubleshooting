# Troubleshooting

Issues
 1. Anaconda spyder issue
    <br/>QOpenGLShaderProgram::uniformLocation(qt_Matrix): shader program is not linked
    <br/>QOpenGLShaderProgram: could not create shader program
    <br/>QOpenGLShader: could not create shader
    <br/>QOpenGLShader: could not create shader
    <br/>shader compilation failed:
    
Solution :
    Add the following lines to anaconda2/lib/python2.7/site-packages/spyder/app
<pre>
try:
    from OpenGL import GL
except:
    pass
import ctypes
ctypes.CDLL("libGL.so.1", mode=ctypes.RTLD_GLOBAL)
</pre>
