---
title: "/BASE(기준 주소) | Microsoft Docs"
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
  - "/base"
  - "VC.Project.VCLinkerTool.BaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/BASE 링커 옵션"
  - "기준 주소용 @ 기호"
  - "기준 주소용 부호"
  - "기준 주소[C++]"
  - "BASE 링커 옵션"
  - "-BASE 링커 옵션"
  - "DLL[C++], 링크"
  - "환경 변수[C++], LIB"
  - "실행 파일[C++], 기준 주소"
  - "키 주소 크기"
  - "LIB 환경 변수"
  - "프로그램[C++], 기준 주소"
  - "프로그램[C++], 재배치 방지"
  - "세미콜론[C++], 지정자"
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
caps.latest.revision: 15
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /BASE(기준 주소)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/BASE:{address[,size] | @filename,key}  
```  
  
 \/BASE 옵션은 프로그램의 기준 주소를 설정합니다. 이 경우 .exe 파일의 기본 위치\(0x400000에서\)나 DLL의 기본 위치\(0x10000000에서\)는 무시됩니다.  운영 체제에서는 지정된 기준 주소나 기본 기준 주소에서 먼저 프로그램을 로드하게 됩니다.  해당 위치에 충분한 공간이 없는 경우에는 프로그램이 재배치됩니다.  프로그램을 재배치하지 않으려면 [\/FIXED](../../build/reference/fixed-fixed-base-address.md) 옵션을 사용합니다.  
  
 주소가 64K의 배수가 아니면 링커에서는 오류를 발생시킵니다.  지정된 크기에 프로그램이 맞지 않으면 링커에서 경고가 발생하도록 프로그램의 크기를 지정할 수도 있습니다.  
  
 명령줄에서 기준 주소를 지정하는 다른 방법은 @ 기호 다음에 *filename*과 파일에 대한 `key`를 사용하는 것입니다.  *filename*은 프로그램에서 사용할 모든 DLL의 위치 및 크기가 포함된 텍스트 파일입니다.  링커는 *filename*을 지정된 경로에서 찾거나 지정된 경로가 없으면 LIB 환경 변수로 지정된 디렉터리에서 찾습니다.  *filename*의 각 줄은 하나의 DLL을 나타내며 구문은 다음과 같습니다.  
  
```  
  
key address [size] ;comment  
```  
  
 `key`는 영숫자 문자열이며 대소문자가 구분되지 않습니다.  대개 DLL 이름을 key로 사용하지만 꼭 그런 것은 아닙니다.  `key` 다음에는 C 언어로 된 16진수 또는 10진수의 기준 주소와 최적화된 최대 `size`가 옵니다.  이 세 인수는 모두 공백이나 탭으로 구분합니다.  링커에서는 지정된 `size`가 프로그램에 필요한 가상 주소 공간보다 작으면 경고를 표시합니다.  `comment`는 세미콜론\(;\)으로 지정하며 한 줄이나 여러 줄로 구성할 수 있습니다.  세미콜론부터 줄 끝 사이에 있는 모든 텍스트는 링커에서 무시됩니다.  다음 예제는 이러한 파일의 일부를 보여 줍니다.  
  
```  
main   0x00010000    0x08000000    ; for PROJECT.exe  
one    0x28000000    0x00100000    ; for DLLONE.DLL  
two    0x28100000    0x00300000    ; for DLLTWO.DLL  
```  
  
 위 줄이 포함된 파일을 DLLS.txt라고 하면 다음 명령은 이 정보를 적용합니다.  
  
```  
link dlltwo.obj /dll /base:@dlls.txt,two  
```  
  
## 설명  
 기준 주소를 할당하면 DLL이 주소 공간을 겹쳐 사용하지 않게 되므로 페이지 수를 줄이고 프로그램의 성능을 향상시킬 수 있습니다.  
  
 기준 주소를 설정하는 다른 방법은 [NAME](../../build/reference/name-c-cpp.md) 또는 [LIBRARY](../../build/reference/library.md) 문에 *BASE* 인수를 사용하는 것입니다.  \/BASE 및 [\/DLL](../../build/reference/dll-build-a-dll.md) 옵션은 모두 **LIBRARY** 문에 해당합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **기준 주소** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)