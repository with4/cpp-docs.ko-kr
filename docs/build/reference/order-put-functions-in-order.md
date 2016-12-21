---
title: "/ORDER(함수에 순서 지정) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.FunctionOrder"
  - "/order"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ORDER 링커 옵션"
  - "LINK 도구[C++], 프로그램 최적화"
  - "LINK 도구[C++], 스왑 조정"
  - "ORDER 링커 옵션"
  - "-ORDER 링커 옵션"
  - "페이징, 최적화"
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ORDER(함수에 순서 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ORDER:@filename  
```  
  
## 매개 변수  
 *filename*  
 COMDAT 함수의 링크 순서를 지정하는 텍스트 파일입니다.  
  
## 설명  
 \/ORDER 옵션을 사용하면 LINK에서는 특정 COMDAT를 미리 정한 순서에 따라 이미지에 배치하여 프로그램을 최적화합니다.  LINK에서는 이미지의 각 섹션 내에 지정된 순서에 따라 함수를 배치합니다.  
  
 COMDAT가 링크할 순서대로 나열된 텍스트 파일\(지시 파일\)인 *filename*에서 순서를 지정합니다.  *filename*의 각 줄마다 하나의 COMDAT 이름이 포함되어 있습니다.  \/Gy 옵션을 사용하여 컴파일한 개체에는 COMDAT가 포함되어 있습니다.  함수 이름은 대\/소문자를 구분합니다.  
  
 LINK에서는 데코레이팅된 형식의 식별자를 사용합니다.  컴파일러에서는 .obj 파일을 만들 때 식별자를 데코레이팅합니다.  링커에 식별자를 지정해야 할 때 데코레이팅된 형식의 식별자를 가져오려면 [DUMPBIN](../../build/reference/dumpbin-reference.md) 도구를 사용합니다.  데코레이팅된 이름에 대한 자세한 내용은 [데코레이팅된 이름](../../build/reference/decorated-names.md)을 참조하십시오.  
  
 \/ORDER를 한 번 이상 지정하면 마지막에 지정된 \/ORDER가 적용됩니다.  
  
 순서를 지정하면 함수에서 호출하는 함수별로 그룹화함으로써 바꾸기를 조정하여 프로그램의 페이징 동작을 최적화할 수 있습니다.  자주 호출하는 함수들을 하나의 그룹으로 묶을 수도 있습니다.  이러한 방법을 사용하면 필요할 때 호출된 함수가 메모리에 있을 가능성이 높아지므로 디스크에서 페이징되지 않아도 됩니다.  
  
 링커에서는 *filename*에 있는 데코레이팅된 이름이 물음표\(?\)나 @ 기호로 시작하지 않는 경우에 한해 모든 데코레이팅된 이름 앞에 밑줄\(\_\)을 추가합니다.  예를 들어, 개체 파일에 `extern "C" int func(int)` 및 `int main(void)`이 포함되어 있는 경우 DUMPBIN [\/SYMBOLS](../../build/reference/symbols.md)을 사용하면 다음의 데코레이팅된 이름이 나열됩니다.  
  
```  
009 00000000 SECT3  notype ()    External     | _func  
00A 00000008 SECT3  notype ()    External     | _main  
```  
  
 그러나 순서 파일에 지정된 이름은 `func` 및 `main`이어야 합니다.  
  
 \/ORDER 옵션을 사용하면 증분 링크를 사용할 수 없습니다.  
  
> [!NOTE]
>  정적 함수 이름이 공용 기호 이름이 아니므로 LINK가 정적 함수의 순서를 지정할 수 없습니다.  \/ORDER를 지정하면 링커에서는 순서 파일에 정적 기호가 있거나 기호를 찾을 수 없는 경우 링커 경고 LNK4037을 표시합니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **최적화** 속성 페이지를 클릭합니다.  
  
4.  **함수 순서** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)