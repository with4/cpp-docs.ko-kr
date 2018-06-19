---
title: 기호 헤더 파일의 이름 바꾸기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing.header
dev_langs:
- C++
helpviewer_keywords:
- resource files, multiple
- Resource Includes dialog box
- symbol header files, changing names
- symbol header files
- header files, changing names
- names [C++], symbol header files
- symbols, symbol header files
- Resource.h
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 953ac59958748bd58fa7e9027c595bf7905e5f27
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864231"
---
# <a name="changing-the-names-of-symbol-header-files"></a>기호 헤더 파일의 이름 변경
일반적으로 모든 기호 정의는 Resource.h에 저장됩니다. 그러나 예를 들어 같은 디렉터리에서 둘 이상의 리소스 파일을 사용할 수 있도록 이 포함 파일 이름을 변경해야 할 수 있습니다.  
  
### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>리소스 기호 헤더 파일의 이름을 변경하려면  
  
1.  [리소스 뷰](../windows/resource-view-window.md).rc 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 [리소스 내용](../windows/resource-includes-dialog-box.md) 바로 가기 메뉴에서.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  에 **기호 헤더 파일** 상자 include 파일에 대 한 새 이름을 입력 합니다.  
  
 관리 되는 프로젝트에 리소스를 추가 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.*  
  
 요구 사항  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [리소스 기호 보기](../windows/viewing-resource-symbols.md)   
 [미리 정의된 기호 ID](../windows/predefined-symbol-ids.md)