---
title: "구성 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.component"
  - "component_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "구성 요소 pragma"
  - "pragma, 구성 요소"
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 구성 요소
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

소스 파일 내에서의 찾아보기 정보 또는 종속성 정보의 수집을 제어합니다.  
  
## 구문  
  
```  
  
      #pragma component( browser, { on | off }[, references [, name ]] )  
#pragma component( minrebuild, on | off )  
#pragma component( mintypeinfo, on | off )  
```  
  
## 설명  
  
## 브라우저  
 수집을 설정하거나 해제할 수 있으며 정보가 수집됨에 따라 특정 이름을 무시하도록 지정할 수 있습니다.  
  
 설정 또는 해제를 사용하면 pragma 정방향에서의 찾아보기 정보 수집을 제어합니다.  예를 들면 다음과 같습니다.  
  
```  
#pragma component(browser, off)  
```  
  
 컴파일러에서 찾아보기 정보 수집을 중지합니다.  
  
> [!NOTE]
>  이 pragma를 통한 찾아보기 정보 수집을 설정하려면 [먼저 찾아보기 정보를 사용할 수 있도록 설정해야 합니다](../build/reference/building-browse-information-files-overview.md).  
  
 **references** 옵션은 *name* 인수 여부에 관계없이 사용될 수 있습니다.  **references**를 *name* 없이 사용하여 참조 수집을 설정하거나 해제합니다\(그러나 다른 찾아보기 정보가 계속 수집됨\).  예를 들면 다음과 같습니다.  
  
```  
#pragma component(browser, off, references)  
```  
  
 컴파일러에서 참조 정보 수집을 중지합니다.  
  
 **references**를 *name* 및 **off**와 함께 사용하여 *name*에 대한 참조가 찾아보기 정보 창에 나타나지 않도록 합니다.  관심 없는 이름 및 형식을 무시하고 찾아보기 정보 파일의 크기를 줄이려면 이 구문을 사용합니다.  예를 들면 다음과 같습니다.  
  
```  
#pragma component(browser, off, references, DWORD)  
```  
  
 해당 지점 정방향부터 **DWORD**에 대한 참조를 무시합니다.  **on**을 사용하여 `DWORD`에 대한 참조 수집을 다시 설정할 수 있습니다.  
  
```  
#pragma component(browser, on, references, DWORD)  
```  
  
 이는 *name*에 대한 참조 수집을 다시 시작하는 유일한 방법입니다. 해제했던 모든 *name*을 명시적으로 설정해야 합니다.  
  
 전처리기에서 *name*을 확장\(예: **NULL**에서 **0**으로의 확장\)하지 않도록 하려면 그 주위에 따옴표를 넣으십시오.  
  
```  
#pragma component(browser, off, references, "NULL")  
```  
  
## 최소 다시 빌드  
 Visual C\+\+ 최소 다시 빌드 기능을 사용하려면 컴파일러에서 C\+\+ 클래스 종속성 정보를 만들고 저장해야 합니다. 이러한 작업은 디스크 공간을 사용합니다.  디스크 공간을 절약하기 위해 예를 들어 변하지 않는 헤더 파일에서와 같이 종속성 정보를 수집할 필요가 없을 때마다 `#pragma component( minrebuild, off )`를 사용할 수 있습니다.  종속성 수집을 다시 설정하기 위해 변하지 않는 클래스 다음에 `#pragma component(minrebuild, on)`를 삽입합니다.  
  
## 형식 정보 감소  
 **mintypeinfo** 옵션으로 인해 지정된 영역에 대한 디버깅 정보가 감소합니다.  이 정보의 양이 상당하므로 .pdb 및 .obj 파일에 영향을 줍니다.  mintypeinfo 영역에서 클래스 및 구조체를 디버깅할 수 없습니다.  mintypeinfo 옵션을 사용하면 다음 경고가 발생하지 않도록 하는 데 도움이 될 수 있습니다.  
  
```  
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information  
```  
  
 자세한 내용은 [최소 다시 빌드 가능](../build/reference/gm-enable-minimal-rebuild.md)\(\/Gm\) 컴파일러 옵션을 참조하십시오.  
  
## 참고 항목  
 [Pragma 지시문 및 \_\_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)