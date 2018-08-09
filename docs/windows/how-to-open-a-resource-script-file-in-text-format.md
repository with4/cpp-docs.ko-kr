---
title: '방법: 리소스 스크립트 파일을 텍스트 형식으로 열기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resource
dev_langs:
- C++
helpviewer_keywords:
- resource script files, opening in text format
- .rc files, opening in text format
- rc files, opening in text format
ms.assetid: 0bc57527-f53b-40c9-99a9-4dcbc5c9af57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 345171742f979e488c6a4bb48cf1b57e4bb2f164
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018112"
---
# <a name="how-to-open-a-resource-script-file-in-text-format"></a>방법: 리소스 스크립트 파일을 텍스트 형식으로 열기
특정 리소스 편집기 내에서 대화 상자와 같은 리소스를 열지 않고 프로젝트의 리소스 스크립트(.rc) 파일의 내용을 보려는 경우가 있을 수 있습니다. 예를 들어 리소스 파일에서 각 대화 상자를 별도로 열지 않고 모든 대화 상자에서 문자열을 검색하려고 할 수 있습니다.  
  
> [!NOTE]
>  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
 텍스트 형식으로 포함 된 모든 리소스를 볼 지 원하는 전역 작업을 수행 하는 리소스 파일을 쉽게 열 수 있습니다 합니다 [텍스트 편집기](http://msdn.microsoft.com/508e1f18-99d5-48ad-b5ad-d011b21c6ab1)합니다.  
  
> [!NOTE]
>  리소스 편집기에서.rc 직접 읽지 않습니다 또는 `resource.h` 파일입니다. 리소스 컴파일러는 리소스 편집기에서 사용되는 이러한 파일을 .aps 파일로 컴파일합니다. 이 파일은 컴파일 단계이며 기호화된 데이터만 저장합니다. 일반적인 컴파일 프로세스에서처럼 기호화되지 않은 정보(예: 주석)는 컴파일 프로세스 중에 삭제됩니다. .aps 파일이 .rc 파일과 동기화되지 않을 때마다 .rc 파일이 다시 생성됩니다. 예를 들어 저장하면 리소스 편집기에서 .rc 파일 및 resource.h 파일을 덮어씁니다. 리소스 자체의 모든 변경 내용은 .rc 파일에 통합된 상태로 유지되지만 주석은 .rc 파일을 덮어쓰면 항상 손실됩니다. 주석을 유지 하는 방법에 대 한 자세한 내용은 [컴파일 타임에 리소스 포함](../windows/how-to-include-resources-at-compile-time.md)합니다.  
  
### <a name="to-open-a-resource-script-file-as-text"></a>리소스 스크립트 파일을 텍스트로 열려면  
  
1.  **파일** 메뉴 **열려**, 클릭 **파일입니다.**  
  
2.  에 **열려 있는 파일** 대화 상자, 텍스트 형식으로 보려는 리소스 스크립트 파일로 이동 합니다.  
  
3.  파일을 선택한 다음 드롭다운 화살표를 클릭 합니다 **열고** 단추 (단추 오른쪽에 있음).  
  
4.  선택할 **연결 프로그램** 드롭 다운 메뉴에서.  
  
5.  에 **열기** 대화 상자, 클릭 **소스 코드 (텍스트) 편집기**합니다.  
  
6.  **형식으로 열기** 드롭 다운 목록에서 **텍스트**합니다.  
  
     리소스에서 열립니다는 **소스 코드** 편집기입니다.  
  
 \- 또는 -  
  
1.  **솔루션 탐색기**,.rc 파일을 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  바로 가기 메뉴에서 선택 **로 열기...** 을 선택한 후 **소스 코드 (텍스트) 편집기**합니다.  
  
## <a name="requirements"></a>요구 사항  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [리소스 편집기](../windows/resource-editors.md)