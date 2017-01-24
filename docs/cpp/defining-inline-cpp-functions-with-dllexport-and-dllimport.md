---
title: "dllexport 및 dllimport로 인라인 C++ 함수 정의 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dllexport 특성[C++], 인라인 함수"
  - "dllimport 특성[C++], 인라인 함수"
  - "함수[C++], 인라인 정의"
  - "인라인 함수[C++], 정의"
ms.assetid: 3b48678b-e7b8-4eda-bb46-b5d34dcf7817
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# dllexport 및 dllimport로 인라인 C++ 함수 정의
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 `dllexport` 특성으로 함수를 인라인으로 정의할 수 있습니다.  이 경우 프로그램의 임의의 모듈이 함수를 참조하는지 여부와 상관없이 함수가 항상 인스턴스화되어 내보내집니다.  함수는 다른 프로그램에서 가져올 수 있는 것으로 간주됩니다.  
  
 **dllimport** 특성으로 선언된 함수를 인라인으로 정의할 수도 있습니다.  이 경우 함수는 \/Ob 지정에 따라 확장될 수 있으나 인스턴스화되지는 않습니다.  특히 인라인으로 가져온 함수의 주소가 사용된 경우 DLL에 상주하는 함수의 주소가 반환됩니다.  이 동작은 인라인으로 가져온 함수가 아닌 함수의 주소를 사용할 때와 동일합니다.  
  
 이러한 규칙은 정의가 클래스 정의 내에서 나타나는 인라인 함수에 적용됩니다.  또한, 인라인 함수의 정적 로컬 데이터 및 문자열은 단일 프로그램\(즉, DLL 인터페이스가 없는 실행 파일\)과 마찬가지로 DLL과 클라이언트 사이에 같은 ID를 유지합니다.  
  
 가져온 인라인 함수를 제공할 때 특별히 주의해야 합니다.  예를 들어 DLL을 업데이트하는 경우 클라이언트에서 DLL의 변경된 버전을 사용하는 것으로 단정하지 마십시오.  적합한 버전의 DLL을 로드하려면 DLL의 클라이언트를 다시 빌드하십시오.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)