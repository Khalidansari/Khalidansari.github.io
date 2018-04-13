---
layout: default
---
# Spring

1. To install it also add commons logging api - else the project will not compile.

2. jar required for aop of spring 3.0 are aspectjweaver.jar,aspectjrt-1.6.0.jar,aopalliance.jar,asm.jar,cglib-2.2.2.jar
    use cglib no dep.
3. If you are implementing interfaces then use JDK Proxy else use CGLIB

Java Dynamic Proxy is a reflective element of the Java language that allows a user to create a proxy of an interface at runtime. 

CGLIB is a code generation library which has the capability to extend Java classes at runtime. Because of this, Spring utilizes this functionality to proxy non-interfaces for its AOP library.

There is a invocationHandler interface with only one method invoke(Proxy, Method, args).

Spring does not apply advice on methods which are called internally. In the below e.g. advice will be applied on AAA but on on the call to BBB which is done from inside AAA:

publc class abc {

    public void AAA() {
        BBB()
    }

    public BBB() {
        Do something
    }
}
---------------------------------------------------
Aspect: The cross cutting concern
Advice: Actual implementation of the aspect
Jointpoint: Where the advice can be plugged in
Pointcut: The jointpoints where we actually plug
Proxy: Is the class which is created after applying the advice

Spring creates the proxy class in runtime and it can do that in two ways:
1. CGLIB - Target class is without interface
2. Java Dynamic Proxy - When target class is using interface

Spring implements AOP Alliance interfaces but supports only method jointpoints (unlike AspectJ or JBoss which even support field jointpoints)

Types:
1. After - AfterReturningAdvice - afterReturning(Object, Method, Object[], Object)
2. Before - BeforeAdvice - before(Method, Object[], Object)
3. Throws - ThrowsAdvice - Marker. Only two method signatures can be used. 
4. Around - MethodInteruptor - invoke(MethodInvocation) the method does not call the actual method automatically; it is to be fired using MethodInvocation.Proceed()