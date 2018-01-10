---
title: "가져오기 라이브러리 및 내보내기 파일 작업 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9e0d60eed00abc60c09e03838a113c424d8f173a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="working-with-import-libraries-and-export-files"></a>가져오기 라이브러리 및 내보내기 파일을 사용한 작업
/DEF 옵션으로 LIB를 사용 하 여 가져오기 라이브러리 및 내보내기 파일을 만들 수 있습니다. LINK 포함 하는 프로그램을 작성 하는 내보내기 파일을 사용 하 여 (일반적으로 동적 연결 라이브러리 (DLL))을 내보내고 가져오기 라이브러리를 사용 하 여 다른 프로그램의 내보내기에 대 한 참조를 확인 합니다.  
  
 Note.dll을 만들기 전에 예비 단계에서 가져오기 라이브러리를 만드는 경우 전달 해야 합니다 개체 파일의 동일한 집합.dll을 빌드할 때 가져오기 라이브러리를 빌드할 때 성공 합니다.  
  
 대부분의 경우 LIB를 사용 하 여 가져오기 라이브러리를 만들 필요가 없습니다. 내보내기를 포함 하는 프로그램 (실행 파일 또는 DLL)을 연결 하면 링크는 내보내기에 설명 하는 가져오기 라이브러리를 자동으로 만듭니다. 나중이 내보내기를 참조 하는 프로그램을 연결 하면 가져오기 라이브러리를 지정 합니다.  
  
 그러나 DLL 가져오기도 수행 하는 프로그램을 내보내는 경우 여부 직접 또는 간접적으로 사용 해야 LIB 가져오기 라이브러리 중 하나를 만드는. LIB 가져오기 라이브러리를 만들 때 또한 내보내기 파일을 만듭니다. Dll 중 하나를 연결 하는 경우에 내보내기 파일을 사용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LIB 참조](../../build/reference/lib-reference.md)