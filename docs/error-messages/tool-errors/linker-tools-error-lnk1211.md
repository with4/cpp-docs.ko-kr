---
title: "링커 도구 오류 LNK1211 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1211"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1211"
ms.assetid: 607400eb-4180-4892-817f-eedfa628af61
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1211
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

미리 컴파일된 형식 정보를 찾을 수 없습니다. 'filename'이\(가\) 링크되지 않았거나 덮어쓰여졌습니다.  
  
 [\/Yc](../../build/reference/yc-create-precompiled-header-file.md)로 컴파일한 지정된 개체 파일이 LINK 명령에 지정되지 않았거나 덮어쓰여졌습니다.  
  
 미리 컴파일된 헤더를 사용하는 디버그 라이브러리를 만들거나 [\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) 및 \/Yc를 지정하면 Visual C\+\+에서 CodeView 디버깅 정보를 포함하는 미리 컴파일된 개체 파일을 생성합니다.  이 오류는 미리 컴파일된 개체 파일을 라이브러리에 저장하거나, 이 라이브러리를 사용하여 실행 파일 이미지를 빌드하거나, 참조되는 개체 파일에 미리 컴파일된 개체 파일에서 정의하는 임의 함수에 대한 전이적 참조가 없는 경우에 발생합니다.  
  
 이 오류는 다음 두 가지 방법을 통해 해결합니다.  
  
-   [\/Yd](../../build/reference/yd-place-debug-information-in-object-file.md) 컴파일러 옵션을 지정하여 미리 컴파일된 헤더의 CodeView 정보를 각 개체 모듈에 추가합니다.  이 방법을 사용하면 일반적으로 응용 프로그램을 링크하는 데 시간이 많이 걸리는 대형 개체 모듈이 생성되므로 그다지 좋은 방법은 아닙니다.  
  
-   함수 정의를 포함하지 않는 미리 컴파일된 헤더 파일을 만드는 경우에는 [\/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md)을 지정하고 임의의 문자열 이름을 전달합니다.  이 방법을 사용하면 컴파일러가 미리 컴파일된 개체 파일에 기호를 만들어 미리 컴파일된 개체 파일과 관련된 미리 컴파일된 헤더 파일을 사용하는 각 개체 파일의 해당 기호에 대한 참조를 내보냅니다.  
  
 **\/Yc** 및 **\/Yl**을 사용하여 모듈을 컴파일하면 컴파일러는 `__@@_PchSym_@00@...@symbol_name`과 유사한 기호를 만듭니다. 여기서 줄임표\(...\)는 컴파일러가 생성하는 문자열을 나타내며 이 문자열은 개체 모듈에 저장됩니다.  이러한 미리 컴파일된 헤더로 컴파일한 소스 파일은 지정된 기호를 참조하므로 링커에 라이브러리의 해당 디버깅 정보와 개체 모듈이 포함됩니다.  
  
 이 오류에 대한 자세한 내용은 기술 자료 문서 Q102697 PRB: Build Errors Using Precompiled Header in Debugging Lib를 참조하십시오.