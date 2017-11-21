---
title: "버전 정보 편집기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.version.F1
dev_langs: C++
helpviewer_keywords:
- Version Information editor, about Version Information editor
- editors, Version Information
- resource editors, Version Information editor
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7280ec93a9e49ae110c2d521695ec696df486950
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="version-information-editor"></a>버전 정보 편집기
버전 정보는 회사 및 제품 ID, 제품 릴리스 번호, 저작권 및 상표 알림 등으로 이루어져 있습니다. 버전 정보 편집기를 사용하면 버전 정보 리소스에 저장되는 이 데이터를 만들고 유지 관리할 수 있습니다. 버전 정보 리소스는 응용 프로그램에 필요하지 않지만 응용 프로그램을 식별하는 정보를 수집하기에 유용한 장소입니다. 버전 정보는 설치 API에도 사용됩니다.  
  
 버전 정보 리소스에는 하나의 상위 블록과 하나 이상의 하위 블록이 있습니다. 위쪽에는 단일 고정 정보 블록이 있고, 아래쪽에는 하나 이상의 버전 정보 블록(다른 언어 및/또는 문자 집합에 대한 정보 블록)이 있습니다. 위쪽 블록에는 편집 가능한 숫자 상자와 선택 가능한 드롭다운 목록이 모두 있습니다. 하위 블록에는 편집 가능한 텍스트 상자만 있습니다.  
  
> [!NOTE]
>  Windows 표준은 VS_VERSION_INFO라고 하는 하나의 버전 리소스만 포함합니다.  
  
 버전 정보 편집기를 사용하면 다음 작업을 수행할 수 있습니다.  
  
-   [버전 정보 리소스의 문자열 편집](../windows/editing-a-string-in-a-version-information-resource.md)  
  
-   [다른 언어의 버전 정보(새 버전 정보 블록) 추가](../windows/adding-version-information-for-another-language.md)  
  
-   [버전 정보 블록 삭제](../windows/deleting-a-version-information-block.md)  
  
-   [프로그램 내에서 버전 정보 액세스](../windows/accessing-version-information-from-within-your-program.md)  
  
    > [!NOTE]
    >  버전 정보 편집기를 사용하는 동안 대개 마우스 오른쪽 단추를 클릭하면 리소스별 명령의 바로 가기 메뉴를 표시할 수 있습니다. 예를 들어 블록 헤더 항목을 가리키는 동안 클릭하면 바로 가기 메뉴에 새 버전 블록 정보 및 버전 블록 정보 삭제 명령이 표시됩니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](https://msdn.microsoft.com/library/f45fce5x.aspx) 에 *.NET Framework 개발자 가이드입니다.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 정보를 참조 하십시오. [데스크톱 앱에 대 한 리소스 파일 만들기](https://msdn.microsoft.com/library/xbx3z216.aspx)합니다. 전역화 및 지역화의 관리 되는 응용 프로그램의 리소스에 대 한 정보를 참조 하십시오. [전역화 및 지역화.NET Framework 응용 프로그램](https://msdn.microsoft.com/library/h6270d0z.aspx)합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [리소스 편집기](../windows/resource-editors.md)   
 [메뉴 및 기타 리소스](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)

