---
title: "방법: 리소스 스크립트 파일을 텍스트 형식으로 열기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.resource
dev_langs:
- C++
helpviewer_keywords:
- resource script files, opening in text format
- .rc files, opening in text format
- rc files, opening in text format
ms.assetid: 0bc57527-f53b-40c9-99a9-4dcbc5c9af57
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 347d33a746adec1208b81fefa54c10472e68b7d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-open-a-resource-script-file-in-text-format"></a>방법: 리소스 스크립트 파일을 텍스트 형식으로 열기
특정 리소스 편집기 내에서 대화 상자와 같은 리소스를 열지 않고 프로젝트의 리소스 스크립트(.rc) 파일의 내용을 보려는 경우가 있을 수 있습니다. 예를 들어 리소스 파일에서 각 대화 상자를 별도로 열지 않고 모든 대화 상자에서 문자열을 검색하려고 할 수 있습니다.  
  
> [!NOTE]
>  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
 포함 된 모든 리소스를 확인 하 고에서 지 원하는 전역 작업을 수행 하기 위해 텍스트 형식으로 쉽게 리소스 파일을 열 수 있습니다는 [텍스트 편집기](http://msdn.microsoft.com/en-us/508e1f18-99d5-48ad-b5ad-d011b21c6ab1)합니다.  
  
> [!NOTE]
>  리소스 편집기에서 .rc 또는 resource.h 파일을 직접 읽지 않습니다. 리소스 컴파일러는 리소스 편집기에서 사용되는 이러한 파일을 .aps 파일로 컴파일합니다. 이 파일은 컴파일 단계이며 기호화된 데이터만 저장합니다. 일반적인 컴파일 프로세스에서처럼 기호화되지 않은 정보(예: 주석)는 컴파일 프로세스 중에 삭제됩니다. .aps 파일이 .rc 파일과 동기화되지 않을 때마다 .rc 파일이 다시 생성됩니다. 예를 들어 저장하면 리소스 편집기에서 .rc 파일 및 resource.h 파일을 덮어씁니다. 리소스 자체의 모든 변경 내용은 .rc 파일에 통합된 상태로 유지되지만 주석은 .rc 파일을 덮어쓰면 항상 손실됩니다. 주석을 유지 하는 방법에 대 한 정보를 참조 하십시오. [컴파일 타임에 리소스를 포함 하 여](../windows/how-to-include-resources-at-compile-time.md)합니다.  
  
### <a name="to-open-a-resource-script-file-as-text"></a>리소스 스크립트 파일을 텍스트로 열려면  
  
1.  **파일** 메뉴 선택 **열려**, 클릭 **파일입니다.**  
  
2.  에 **열려 있는 파일** 대화 상자, 텍스트 형식으로 보려는 리소스 스크립트 파일을 찾습니다.  
  
3.  드롭다운 화살표를 클릭 한 다음 파일을 강조 표시는 **열려** 단추 (단추의 오른쪽에 있음).  
  
4.  선택 **프로그램** 드롭 다운 메뉴에서 합니다.  
  
5.  에 **프로그램** 대화 상자를 클릭 **소스 코드 (텍스트) 편집기**합니다.  
  
6.  **형식으로 열기** 드롭 다운 목록 **텍스트**합니다.  
  
     리소스가 소스 코드 편집기에서 열립니다.  
  
 \- 또는 -  
  
1.  **솔루션 탐색기**를.rc 파일을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴에서 선택 **연결 프로그램...** 을 선택한 후 **소스 코드 (텍스트) 편집기**합니다.  
  

  
 요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [리소스 편집기](../windows/resource-editors.md)