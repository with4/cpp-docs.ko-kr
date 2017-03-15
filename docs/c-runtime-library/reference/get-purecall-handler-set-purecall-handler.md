---
title: "_set_purecall_handler, _get_purecall_handler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_purecall_handler"
  - "_set_purecall_handler_m"
  - "_get_purecall_handler"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_set_purecall_handler"
  - "_set_purecall_handler_m"
  - "set_purecall_handler_m"
  - "set_purecall_handler"
  - "stdlib/_set_purecall_handler"
  - "stdlib/_get_purecall_handler"
  - "_get_purecall_handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_set_purecall_handler 함수"
  - "set_purecall_handler 함수"
  - "purecall_handler"
  - "set_purecall_handler_m 함수"
  - "_purecall_handler"
  - "_set_purecall_handler_m 함수"
  - "_get_purecall_handler 함수"
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _set_purecall_handler, _get_purecall_handler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

순수 가상 함수 호출에 대 한 오류 처리기를 가져오거나 설정 합니다.  
  
## 구문  
  
```  
typedef void (__cdecl* _purecall_handler)(void);  
  
_purecall_handler __cdecl _get_purecall_handler(void);  
  
_purecall_handler __cdecl _set_purecall_handler(   
   _purecall_handler function  
);  
```  
  
#### 매개 변수  
 `function`  
 순수 가상 함수 호출 시 호출되는 함수입니다.`_purecall_handler` 함수에 void 반환 형식이 있어야 합니다.  
  
## 반환 값  
 이전 처리기가 없는 경우 `_purecall_handler`는`nullptr`을 반환합니다.  
  
## 설명  
 `_get_purecall_handler` 및 `_set_purecall_handler` 함수는 Microsoft 전용 및 c \+ \+ 코드에만 적용 됩니다.  
  
 순수 가상 함수에 대 한 호출 구현이 없는 되었기 때문에 오류입니다. 기본적으로 컴파일러는 순수 가상 함수를 호출할 때에 오류 처리기 함수를 호출 하는 프로그램을 종료 하는 코드를 생성 합니다. 사용자 고유의 오류 처리기 함수에 대 한 순수 가상 함수 호출, 디버깅 또는 보고를 목적으로 catch를 설치할 수 있습니다. 고유한 오류 처리기를 사용 하려면이 있는 함수를 만듭니다는 `_purecall_handler` 서명을 사용 하 여 `_set_purecall_handler` 현재 처리기 되도록 합니다.  
  
 하나씩만 있기 때문에 `_purecall_handler` 호출 하는 경우 각 프로세스에 대 한 `_set_purecall_handler` 모든 스레드가 즉시 영향을 미치기 합니다. 스레드의 마지막 호출자가 처리기를 설정합니다.  
  
 기본 동작을 복원 하려면 호출 `_set_purecall_handler` 를 사용 하 여 한 `nullptr` 인수입니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|`_get_purecall_handler`, `_set_purecall_handler`|\< d l i b \> 또는 \< stdlib.h \>|  
  
 호환성에 대한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.  
  
## 예제  
  
```  
// _set_purecall_handler.cpp  
// compile with: /W1  
#include <tchar.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
class CDerived;  
class CBase  
{  
public:  
   CBase(CDerived *derived): m_pDerived(derived) {};  
   ~CBase();  
   virtual void function(void) = 0;  
  
   CDerived * m_pDerived;  
};  
  
class CDerived : public CBase  
{  
public:  
   CDerived() : CBase(this) {};   // C4355  
   virtual void function(void) {};  
};  
  
CBase::~CBase()  
{  
   m_pDerived -> function();  
}  
  
void myPurecallHandler(void)  
{  
   printf("In _purecall_handler.");  
   exit(0);  
}  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
   _set_purecall_handler(myPurecallHandler);  
   CDerived myDerived;  
}  
```  
  
```Output  
In _purecall_handler.  
```  
  
## 참고 항목  
 [오류 처리](../../c-runtime-library/error-handling-crt.md)   
 [\_purecall](../../c-runtime-library/reference/purecall.md)