---
title: "링커 도구 경고 LNK4070 | Microsoft Docs"
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
  - "LNK4070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4070"
ms.assetid: f95f179a-fff9-427e-bd51-466b3934517f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/OUT: .EXP의 filename 지시문이 'filename' 출력 파일 이름과 다릅니다. 지시문이 무시됩니다.  
  
 .exp 파일을 만들 때 [NAME](../../build/reference/name-c-cpp.md) 또는 [LIBRARY](../../build/reference/library.md) 문에 지정한 `filename`이 기본적으로 선택되었거나 [\/OUT](../../build/reference/out-output-file-name.md) 옵션으로 지정한 출력 `filename`과 다릅니다.  
  
 개발 환경에서 출력 파일의 이름을 변경했는데 프로젝트의 def 파일이 업데이트되지 않은 경우 이 경고가 발생합니다.  이 경고를 해결하려면 .def 파일을 수동으로 업데이트하십시오.  
  
 결과로 생성된 DLL을 사용하는 클라이언트 프로그램에 문제가 발생할 수 있습니다.