---
title: "Registry Scripting Examples | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "registrar scripts [ATL]"
  - "레지스트리, Registrar"
  - "스크립팅, 예제"
  - "스크립트, Registrar scripts"
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Registry Scripting Examples
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목의 스크립팅 예제 시스템 레지스트리에 키를 추가, 등록자 COM 서버를 등록 하 고 여러 구문 분석 트리를 지정 하는 방법을 보여 줍니다.  
  
## HKEY\_CURRENT\_USER에 키를 추가 합니다.  
 단일 키 시스템 레지스트리에 추가 하는 간단한 스크립트를 다음 구문 분석 트리를 보여 줍니다.  특히, 키, 스크립트를 추가 `MyVeryOwnKey`에, `HKEY_CURRENT_USER`.  또한 기본 문자열 값을 할당 `HowGoesIt?` 새 키.  
  
```  
HKEY_CURRENT_USER  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
```  
  
 이 스크립트는 여러 하위 키를 다음과 같이 정의를 쉽게 확장할 수 있습니다.  
  
```  
HKCU  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
   {  
      'HasASubkey'  
      {  
         'PrettyCool?' = d '55'  
         val 'ANameValue' = s 'WithANamedValue'  
      }  
   }  
}  
```  
  
 이제 스크립트는 하위 키를 추가 `HasASubkey`에, `MyVeryOwnKey`.  모두 추가이 하위 키에는 `PrettyCool?` 하위 키 \(기본값 `DWORD` 55의 값\)와 `ANameValue` 라는 값 \(문자열 값이 `WithANamedValue`\).  
  
##  <a name="_atl_register_the_registrar_com_server"></a> 등록자 COM 서버를 등록 합니다.  
 다음 스크립트에서는 등록자 COM 서버를 등록합니다.  
  
```  
HKCR  
{  
   ATL.Registrar = s 'ATL Registrar Class'  
   {  
      CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'  
   }  
   NoRemove CLSID  
   {  
      ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} =  
                   s 'ATL Registrar Class'  
      {  
         ProgID = s 'ATL.Registrar'  
         InprocServer32 = s '%MODULE%'  
         {  
            val ThreadingModel = s 'Apartment'  
         }  
      }  
   }  
}  
```  
  
 런타임에,이 구문 분석 트리 추가 `ATL.Registrar` 키를 `HKEY_CLASSES_ROOT`.  이 새 키에 다음 it.  
  
-   지정 `ATL Registrar Class` 키의 기본 문자열 값입니다.  
  
-   추가 `CLSID` 하위 키로.  
  
-   Specifies `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` for `CLSID`.  \(등록자의 값인 CLSID 사용 `CoCreateInstance`.\)  
  
 이후 `CLSID` 는 공유 하 고, 해당 등록 취소 모드에서 제거할 수 없습니다.  문, `NoRemove CLSID`,이 하를 나타내는 하지 `CLSID` 레지스터 모드로 열 및 등록 취소 모드에서 무시 해야 합니다.  
  
 `ForceRemove` 문을 키 및 모든 하위 키를 다시 만들기 전에 제거 하 여 정리 작업 기능을 제공 합니다.  이 하위 키의 이름을 변경 하면 유용 합니다.  이 스크립트 예제에서는 `ForceRemove` 확인 하는 경우 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 이미 있습니다.  If it does, `ForceRemove`:  
  
-   재귀적으로 삭제 합니다. `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 및 모든 하위 키입니다.  
  
-   다시 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  
  
-   추가 `ATL Registrar Class` 에 대 한 기본 문자열 값으로 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  
  
 구문 분석 트리는 이제 두 개의 새 하위 키를 추가 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  첫 번째 키를 `ProgID`, ProgID 기본 문자열 값을 가져옵니다.  두 번째 키를 `InprocServer32`, 기본 문자열 값을 가져옵니다 `%MODULE%`, 즉 전처리기 값 섹션에서 설명한  [바꿀 수 있는 매개 \(등록자 전처리기\)를 사용 하 여](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md),이 문서의.  `InprocServer32`또한 명명 된 값을 가져옵니다 `ThreadingModel`, 문자열 값을 `Apartment`.  
  
## 여러 구문 분석 트리를 지정 합니다.  
 스크립트에서 두 개 이상의 구문 분석 트리를 지정 하려면 단순히 하나의 트리 다른 끝에 배치 합니다.  예를 들어, 다음 스크립트는 키 추가 `MyVeryOwnKey`, 둘 다 구문 분석 트리를 `HKEY_CLASSES_ROOT` 및 `HKEY_CURRENT_USER`.  
  
```  
HKCR  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
HKEY_CURRENT_USER  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
```  
  
> [!NOTE]
>  등록자 스크립트에서 최대 토큰 크기는 4k입니다.  \(토큰 구문에서 인식이 가능한 요소입니다.\) 이전 스크립트 예제에서 `HKCR`, `HKEY_CURRENT_USER`, `'MyVeryOwnKey'`, 및 `'HowGoesIt?'` 모든 토큰입니다.  
  
## 참고 항목  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)