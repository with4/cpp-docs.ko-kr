---
title: 형식 지정 또는 특수 문자를 문자열로 추가 | Microsoft Docs
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
ms.openlocfilehash: 429ba8d836579bd3bc1d1dd8844494bf9cd17a7a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864599"
---
# <a name="adding-formatting-or-special-characters-to-a-string"></a>문자열에 형식 지정 또는 특수 문자 추가
### <a name="to-add-formatting-or-special-characters-to-a-string"></a>문자열에 형식 지정 또는 특수 문자를 추가 하려면  
  
1.  해당 아이콘을 두 번 클릭 하 여 문자열 테이블을 엽니다 [리소스 뷰](../windows/resource-view-window.md)합니다.  
  
    > [!NOTE]
    >  프로젝트에 .rc 파일이 아직 없는 경우 [새 리소스 스크립트 파일 만들기](../windows/how-to-create-a-resource-script-file.md)를 참조하세요.  
  
2.  수정 하려는 문자열을 선택 합니다.  
  
3.  에 [속성 창](/visualstudio/ide/reference/properties-window), 표준 이스케이프 시퀀스 아래에 나열 된 텍스트에 추가 **캡션** 상자 및 키를 눌러 **ENTER**합니다.  
  
    |이|다음과 같이 입력|  
    |-----------------|---------------|  
    |줄 바꿈|\n|  
    |캐리지 리턴|\r|  
    |탭|\t|  
    |백슬래시(\\)|\\\|  
    |ASCII 문자|\ddd (8 진수 표기법)|  
    |경고 (벨)|\a|  
  
> [!NOTE]
>  문자열 편집기 ASCI 문자로 이스케이프의 전체 집합을 지원 하지 않습니다. 위에 나열 된만 사용할 수 있습니다.  
  
 관리 되는 프로젝트 (공용 언어 런타임을 대상으로 프로젝트)에 리소스를 추가 하는 방법에 대 한 정보를 참조 하십시오 [데스크톱 응용 프로그램의 리소스](/dotnet/framework/resources/index) 에 *.NET Framework 개발자 가이드입니다.* 를 참조하세요. 관리되는 프로젝트에 리소스 파일 추가, 리소스 액세스, 정적 리소스 표시, 속성에 리소스 문자열 할당 등의 작업을 수동으로 수행하는 방법에 대한 자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5) 및 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 **요구 사항**  
  
 Win32  
  
## <a name="see-also"></a>참고 항목  
 [문자열 편집기](../windows/string-editor.md)   

