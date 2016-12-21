---
title: "/IGNORE(특정 경고 무시) | Microsoft Docs"
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
  - "/ignore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IGNORE 링커 옵션"
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /IGNORE(특정 경고 무시)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IGNORE:warning[,warning]  
```  
  
## 매개 변수  
 `warning`  
 표시하지 않을 링커 경고의 번호로 범위가 4000~4999입니다.  
  
## 설명  
 기본적으로 LINK는 모든 경고를 보고합니다.  링커가 특정 경고 번호를 표시하지 않도록 명령하려면 **\/IGNORE:**`warning`을 지정합니다.  여러 경고를 무시하려면 경고 번호를 쉼표로 구분합니다.  
  
 일부 경고는 링커에서 무시할 수 없습니다.  아래 테이블에는 **\/IGNORE**를 사용해도 표시되어 버리는 경고가 나열됩니다.  
  
|링커 경고||  
|-----------|-|  
|LNK4017|대상 플랫폼에 지원되지 않는 `keyword` 문\(무시됨\)|  
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|인식할 수 없는 옵션 '`option`'입니다. 무시합니다.|  
|LNK4062|'`architecture`'이\(가\) '`option`' 대상 컴퓨터와 호환되지 않습니다. 옵션은 무시됩니다.|  
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|"`option1`"이\(가\) "`option2`" 사양으로 인해 무시됩니다.|  
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|'`function`' 진입점이 '`number`'바이트 인수가 있는 \_\_stdcall이 아닙니다. 이미지가 실행되지 않을 수도 있습니다.|  
|LNK4088|\/FORCE 옵션을 사용하여 생성하는 이미지입니다. 이미지가 실행되지 않을 수도 있습니다.|  
|[LNK4105](../../error-messages/tool-errors/linker-tools-warning-lnk4105.md)|'`option`' 옵션에 지정된 인수가 없습니다. 스위치가 무시됩니다.|  
|LNK4203|'`filename`' 프로그램 데이터베이스를 읽는 동안 오류가 발생했습니다. 디버그 정보가 없는 것처럼 개체를 링크합니다.|  
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|'`filename`'에 참조 모듈에 대한 디버깅 정보가 없습니다. 디버깅 정보가 없는 것처럼 개체를 링크합니다.|  
|[LNK4205](../../error-messages/tool-errors/linker-tools-warning-lnk4205.md)|'`filename`'에 참조 모듈에 대한 현재 디버깅 정보가 없습니다. 디버깅 정보가 없는 것처럼 개체를 링크합니다.|  
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|미리 컴파일된 형식 정보를 찾을 수 없습니다. '`filename`'이\(가\) 링크되지 않았거나 덮어쓰여졌습니다. 디버그 정보가 없는 것처럼 개체를 링크합니다.|  
|LNK4207|'`filename`'이\(가\) \/Yc \/Yu \/Z7을 사용하여 컴파일했습니다. PDB를 만들 수 없습니다. \/Zi를 사용하여 다시 컴파일하십시오. 디버그 정보가 없는 것처럼 개체를 링크합니다.|  
|LNK4208|'`filename`'에 호환되지 않는 PDB 형식이 있습니다. 삭제한 다음 다시 빌드하십시오. 디버그 정보가 없는 것처럼 개체를 링크합니다.|  
|LNK4209|디버깅 정보가 손상되었습니다. 모듈을 다시 컴파일하십시오. 디버그 정보가 없는 것처럼 개체를 링크합니다.|  
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option`은\(는\) 더 이상 지원되지 않습니다. 무시됩니다.|  
|LNK4228|'`option`'은\(는\) DLL에 사용할 수 없습니다. 무시됩니다.|  
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|잘못된 지시문 \/`directive`이\(가\) 발견되었습니다. 무시됩니다.|  
  
 일반적으로 무시할 수 없는 링커 경고는 해결해야 하는 빌드 오류, 명령줄 오류 또는 구성 오류를 나타냅니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **링커** 폴더에서 **명령줄** 속성 페이지를 선택합니다.  
  
3.  **추가 옵션** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하십시오.