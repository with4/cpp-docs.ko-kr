---
title: '방법: 컴파일 타임에 리소스 포함 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.resvw.resource.including
- vc.resvw.resource.including
dev_langs:
- C++
helpviewer_keywords:
- compiling source code, including resources
- comments [C++], compiled files
- resources [Visual Studio], including at compile time
- projects [C++], including resources
- '#include directive'
- include directive (#include)
ms.assetid: 357e93c2-0a29-42f9-806f-882f688b8924
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 765d78ef5371015fdce3e505e7a2454c29c6c97e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-include-resources-at-compile-time"></a>방법: 컴파일 타임에 리소스 포함
일반적으로 하나의 리소스 스크립트(.rc) 파일에서 모든 리소스의 기본 배열을 사용하는 것이 쉽고 편리합니다. 그러나에 추가할 수 있습니다 리소스 다른 파일에 있는 현재 프로젝트 컴파일 타임에 나열 된 **컴파일 타임 지시문** 상자에 [리소스 내용 대화 상자](../windows/resource-includes-dialog-box.md)합니다.  
  
 다음과 같은 여러 가지 이유로 주 .rc 파일이 아닌 다른 파일에 리소스를 배치합니다.  
  
-   .rc 파일을 저장할 때 삭제되지 않는 리소스 문에 주석을 추가하기 위해서입니다.  
  
     리소스 편집기에서 .rc 또는 resource.h 파일을 직접 읽지 않습니다. 리소스 컴파일러는 리소스 편집기에서 사용되는 이러한 파일을 .aps 파일로 컴파일합니다. 이 파일은 컴파일 단계이며 기호화된 데이터만 저장합니다. 일반적인 컴파일 프로세스에서처럼 기호화되지 않은 정보(예: 주석)는 컴파일 프로세스 중에 삭제됩니다. .aps 파일이 .rc 파일과 동기화되지 않을 때마다 .rc 파일이 다시 생성됩니다. 예를 들어 저장하면 리소스 편집기에서 .rc 파일 및 resource.h 파일을 덮어씁니다. 리소스 자체의 모든 변경 내용은 .rc 파일에 통합된 상태로 유지되지만 주석은 .rc 파일을 덮어쓰면 항상 손실됩니다.  
  
-   이미 개발되고 테스트되어 추가로 수정할 필요가 없는 리소스를 포함하기 위해서입니다. 포함되었지만 .rc 확장명이 없는 모든 파일은 리소스 편집기에서 편집할 수 없습니다.  
  
-   여러 가지 다른 프로젝트에서 사용되고 있거나 소스 코드 버전 제어 시스템의 일부인 리소스를 포함하기 위해서 입니다. 따라서 수정 사항이 모든 프로젝트에 영향을 줄 수 있는 중앙 위치에 있어야 합니다.  
  
-   사용자 지정 형식인 리소스(예: RCDATA 리소스)를 포함하기 위해서입니다. RCDATA 리소스에는 특별한 요구 사항이 있을 수 있습니다. 예를 들어 nameID 필드의 값으로 식을 사용할 수 없습니다. 자세한 내용은 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] 설명서를 참조하세요.  
  
 이러한 조건 중 하나라도 충족 하는 기존.rc 파일에 섹션이 있으면 섹션 하나에 배치 해야 또는 이상의 별도.rc 파일 및 사용 하 여 프로젝트에 포함 된 [리소스 내용 대화 상자](../windows/resource-includes-dialog-box.md)합니다. *Projectname*새 프로젝트의 \res 하위 디렉터리에서 만든.rc2 파일이 이러한 용도로 사용 됩니다.  
  
### <a name="to-include-resources-in-your-project-at-compile-time"></a>컴파일 시간에 프로젝트에 리소스를 포함하려면  
  
1.  고유한 파일 이름으로 리소스 스크립트 파일에 리소스를 배치합니다. 사용 하지 마십시오 *projectname*.rc,이 주 리소스 스크립트 파일에 사용 되는 파일 이름 이므로 합니다.  
  
2.  .Rc 파일을 마우스 오른쪽 단추로 클릭 (에서 [리소스 뷰](../windows/resource-view-window.md)) 선택 하 고 **리소스 내용** 바로 가기 메뉴에서.  
  
3.  에 **컴파일 타임 지시문** 상자에서 추가 [#include](../preprocessor/hash-include-directive-c-cpp.md) 컴파일러 지시문을 개발 환경에서 주 리소스 파일에 새 리소스 파일을 포함 합니다.  
  
     이런 식으로 포함된 파일의 리소스는 컴파일 시간에 실행 파일의 일부가 됩니다. 이러한 리소스는 프로젝트의 주 .rc 파일에서 작업할 때 직접 편집하거나 수정할 수 없습니다. 포함된 .rc 파일을 별도로 열어야 합니다. 포함되었지만 .rc 확장명이 없는 모든 파일은 리소스 편집기에서 편집할 수 없습니다.  
  

  
 요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [리소스 파일](../windows/resource-files-visual-studio.md)   
 [리소스 편집기](../windows/resource-editors.md)