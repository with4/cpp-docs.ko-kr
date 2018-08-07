---
title: 문자열에 형식 지정 또는 특수 문자를 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35592793b0fe606d3b88bef900d528d2c1231406
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463842"
---
# <a name="adding-formatting-or-special-characters-to-a-string"></a>문자열에 형식 지정 또는 특수 문자 추가
### <a name="to-add-formatting-or-special-characters-to-a-string"></a>문자열에 형식 지정 또는 특수 문자를 추가 하려면  
  
1.  문자열 테이블에서 해당 아이콘을 두 번 클릭 하 여 [리소스 뷰](../windows/resource-view-window.md)합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  수정 하려는 문자열을 선택 합니다.  
  
3.  에 [속성 창](/visualstudio/ide/reference/properties-window), 텍스트에 아래 나열 된는 모든 표준 이스케이프 시퀀스를 추가 합니다 **캡션** 상자 및 키를 누릅니다 **ENTER**.  
  
    |이 가져오려면|이 입력|  
    |-----------------|---------------|  
    |줄 바꿈|\n|  
    |캐리지 리턴|\r|  
    |탭|\t|  
    |백슬래시(\\)|\\\|  
    |ASCII 문자|\ddd (8 진수 표기법)|  
    |경고 (벨)|\a|  
  
> [!NOTE]
>  문자열 편집기는 이스케이프 된 ASCI 문자로의 전체 집합을 지원 하지 않습니다. 위에 나열 된만 사용할 수 있습니다.  
  
 (대상으로 하는 공용 언어 런타임) 관리 되는 프로젝트에 리소스를 추가 하는 방법에 대 한 정보를 참조 하세요 [데스크톱 앱의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드.* 수동으로 관리 되는 프로젝트에 리소스 파일을 추가, 리소스 액세스, 정적 리소스 표시 및 속성에 리소스 문자열 할당에 대 한 내용은 참조 하세요 [연습: Windows Forms 지역화](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) 고[연습: ASP.NET에서 지역화에 리소스를 사용 하 여](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)입니다.  
  
 **요구 사항**  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [문자열 편집기](../windows/string-editor.md)   

