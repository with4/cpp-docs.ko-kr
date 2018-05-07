---
title: HTML 기초 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML [MFC], about HTML
ms.assetid: aab8ea9f-12d4-4bdd-a585-ac3124081a2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c59004f27e0f3a1c629daae621df831fe82cd7a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="html-basics"></a>HTML 기초
대부분의 브라우저는 검색 중인 페이지의 HTML 소스를 검사 하는 기능이 있습니다. HTML (Hypertext markup language) 태그의 수를 표시 하는 소스를 볼 때 텍스트와 섞여 꺾쇠 괄호 (<>)으로 둘러싸여 있습니다.  
  
 다음 단계에서는 HTML 태그를 사용 하 여 간단한 웹 페이지를 작성 합니다. 이 단계에서는 있습니다 수 일반 텍스트 파일을 메모장에서에서를 입력, 몇 가지 변경, 파일을 저장 및 변경 내용을 보려면 브라우저에서 페이지를 다시 로드 합니다.  
  
#### <a name="to-create-an-html-file"></a>HTML 파일을 만들려면  
  
1.  메모장 이나 일반 텍스트 편집기를 엽니다.  
  
2.  **파일** 메뉴 선택 `New`합니다.  
  
3.  다음 줄을 입력 합니다.  
  
 ```  
 <HTML>  
 <HEAD>  
 <TITLE>Top HTML Tags</TITLE>  
 </HEAD>  
 </HTML>  
 ```  
  
4.  **파일** 메뉴 선택 **저장**, c:\webpages\First.htm로 파일을 저장 하 고 있습니다. 파일을 편집기에서 열어 둡니다.  
  
5.  브라우저와 스위치는 **파일** 메뉴에서 선택 **열려**, 또는 형식 `file://C:/webpages/first.htm` 브라우저의 URL 편집 상자에 있습니다. "상위 HTML 태그입니다." 창 캡션 사용 하 여 빈 페이지가 표시 됩니다.  
  
     태그 쌍을 꺾쇠 괄호에 포함 된 방식을 살펴봅니다. 태그는 대/소문자를 구분 하지 않지만 대/소문자는 대개 태그를 강조 하기.  
  
     태그 \<HTML > 시작 태그와 문서를 \</HTML >에서 종료 합니다. (항상 필수는 아님) 끝 태그 시작 태그와 동일 하지만 태그 앞에 슬래시 (/)가 있습니다. 꺾쇠 괄호 (<)과 태그를 쿼리의 시작 사이 공백이 없어야 없어야 합니다.  
  
6.  다시 메모장으로 전환한 후는  \< /H > 줄을 입력 합니다.  
  
 ```  
 <BODY>  
    HTML is swell.  
    Life is good.  
 </BODY>  
 ```  
  
7.  **파일** 메뉴 선택 **저장**합니다.  
  
8.  브라우저로 다시 전환 하 고 페이지를 새로 고칩니다.  
  
     브라우저 창의 클라이언트 영역에 표시 됩니다. 프로그램 캐리지 리턴는 무시 됩니다. 줄 바꿈을 할 경우에 포함 해야는 `<BR>` 이후 첫 번째 줄은 태그입니다.  
  
     에 따라, 사이 모든 위치에서 텍스트를 삽입 하는 모든 단계에 대 한 \<본문 > 및  \< /본문 > 문서 본문에 추가 하 합니다.  
  
9. 헤더를 추가 합니다.  
  
 ```  
 <H3>Here's the big picture</H3>  
 ```  
  
10. 페이지와 같은 디렉터리에 저장 된.gif 파일을 사용 하 여 이미지를 추가 합니다.  
  
 ```  
 <IMG src="yourfile.gif">  
 ```  
  
11. 목록을 추가 합니다.  
  
 ```  
 <UL>Make me an unordered list.  
 <LI>One programmer</LI>  
 <LI>Ten SDKs</LI>  
 <LI>Great Internet Apps</LI>  
 </UL>  
 ```  
  
12. 목록 번호 매기기 대신를 사용 하 여 쌍으로 \<OL > 및 \</OL > 자리에 태그를 삽입는 \<u L > 및 \</UL > 태그입니다.  
  
 시작 하는 받아야 합니다. 훌륭한 기능 웹 페이지에 표시 되 면 HTML 소스를 검사 하 여 만든 방법을 알아볼 수 있습니다. Microsoft 기본 페이지 같은 HTML 편집기 간단 하 고 고급 페이지를 만드는 데 사용할 수 있습니다.  
  
 구축한 경험이 파일에 대 한 전체 HTML 소스는 다음과 같습니다.  
  
```  
<HTML>  
<HEAD>  
<TITLE>Top HTML Tags</TITLE>  
</HEAD>  
<BODY>  
HTML is swell.<BR>  
Life is good.  
<H3>Here's the big picture</H3>  
<IMG src="yourfile.gif">  
<UL>Make me an unordered list.  
<LI>One programmer</LI>  
<LI>Ten SDKs</LI>  
<LI>Great Internet Apps</LI>  
</UL>  
</BODY>  
</HTML>  
```  
  
 태그, 특성 및 확장에 대 한 전체 설명은, Hypertext Markup Language (HTML) 사양을 참조 하십시오.  
  
 [http://www.w3.org/pub/WWW/MarkUp/](http://www.w3.org/pub/www/markup/)  
  
## <a name="see-also"></a>참고 항목  
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)

