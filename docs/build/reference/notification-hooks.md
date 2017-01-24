---
title: "알림 후크 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "지연 DLL 로드, 알림 후크"
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 알림 후크
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

알림 후크는 도우미 루틴에서 다음 동작이 발생하기 바로 전에 호출됩니다.  
  
-   라이브러리에 대한 저장 핸들이 이미 로드되어 있는지 확인합니다.  
  
-   DLL을 로드하기 위해 **LoadLibrary**가 호출됩니다.  
  
-   프로시저의 주소를 가져오기 위해 **GetProcAddress**가 호출됩니다.  
  
-   지연 가져오기 로드 썽크로 제어를 반환합니다.  
  
 알림 후크는 다음과 같은 경우에 활성화됩니다.  
  
-   알림을 수신하는 사용자 함수를 가리키도록 초기화되는 **\_\_pfnDliNotifyHook2** 포인터의 새 정의를 제공하는 경우  
  
     또는  
  
-   프로그램이 지연 로드 중인 DLL을 호출하기 전에 **\_\_pfnDliNotifyHook2** 포인터를 해당 후크 함수로 설정하는 경우  
  
 알림이 **dliStartProcessing**인 경우 후크 함수는 다음 값을 반환합니다.  
  
 NULL  
 기본 도우미가 DLL 로드를 처리합니다.  알림 목적으로만 호출하는 경우에 유용합니다.  
  
 함수 포인터  
 기본 지연 로드 처리를 생략합니다.  이렇게 하면 사용자가 직접 작성한 로드 처리기를 제공할 수 있습니다.  
  
 알림이 **dliNotePreLoadLibrary**인 경우 후크 함수는 다음 값을 반환합니다.  
  
-   0 \- 알림 목적으로만 사용하는 경우  
  
-   로드된 DLL의 HMODULE \- DLL 자체를 로드한 경우  
  
 알림이 **dliNotePreGetProcAddress**인 경우 후크 함수는 다음 값을 반환할 수 있습니다.  
  
-   0 \- 알림 목적으로만 사용하는 경우  
  
-   가져온 함수의 주소 \- 후크 함수가 주소 자체를 가져오는 경우  
  
 알림이 **dliNoteEndProcessing**인 경우 후크 함수의 반환 값은 무시됩니다.  
  
 이 포인터가 0이 아닌 값으로 초기화되면 지연 로드 도우미는 실행하는 동안 특정 알림 시점에서 함수를 호출합니다.  함수 포인터는 다음과 같이 정의됩니다.  
  
```  
// The "notify hook" gets called for every call to the  
// delay load helper.  This allows a user to hook every call and  
// skip the delay load helper entirely.  
//  
// dliNotify == {  
//  dliStartProcessing |  
//  dliNotePreLoadLibrary  |  
//  dliNotePreGetProc |  
//  dliNoteEndProcessing}  
//  on this call.  
//  
ExternC  
PfnDliHook   __pfnDliNotifyHook2;  
  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 알림은 알림 값과 함께 **DelayLoadInfo** 구조체 형식으로 후크 함수에 전달됩니다.  이 데이터는 지연 로드 도우미 루틴이 사용하는 데이터와 동일합니다.  알림 값은 [구조체 및 상수 정의](../../build/reference/structure-and-constant-definitions.md)에 정의된 값 중 하나입니다.  
  
## 참고 항목  
 [오류 처리 및 알림](../../build/reference/error-handling-and-notification.md)