---
title: "링커 도구 오류 LNK1256 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "xml"
  - "LNK1256"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1256"
ms.assetid: 55b64b2b-a56b-436c-a55e-ec9c6dcb050e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1256
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ALINK 작업이 실패했습니다: 이유  
  
 LNK1256이 발생하는 일반적인 이유는 어셈블리의 버전 번호가 잘못되었기 때문입니다.  어셈블리 버전 번호에는 65535 값을 포함할 수 없습니다.  어셈블리 버전의 유효한 범위는 0~65534입니다.  
  
 ALINK가 명명된 키 컨테이너를 찾을 수 없는 경우에도 LNK1256이 발생할 수 있습니다.  키 컨테이너를 삭제한 다음 [Sn.exe\(강력한 이름 도구\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)를 사용하여 강력한 이름 CSP에 다시 추가합니다.  
  
 링커와 Alink.dll 간에 버전이 일치하지 않는 경우에도 LNK1256이 발생할 수 있습니다.  설치된 Visual Studio가 손상되면 버전이 일치하지 않을 수 있습니다.  Windows 제어판의 **프로그램 및 기능**을 사용하여 Visual Studio를 복구하거나 다시 설치합니다.  
  
 다음 샘플에서는 LNK1256을 생성합니다.  
  
```  
// LNK1256.cpp  
// compile with: /clr /LD  
// LNK1256 expected  
[assembly:System::Reflection::AssemblyVersionAttribute("1.0.65535")];  
public class CMyClass {  
public:  
   int value;  
};  
```