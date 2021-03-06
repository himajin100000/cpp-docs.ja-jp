---
title: UNIX | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unix
dev_langs:
- C++
helpviewer_keywords:
- UNIX
- POSIX compatibility
- POSIX file names
- UNIX, compatibility
ms.assetid: 40792414-7a5b-415d-bfa8-2bfb1ebb3731
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f5155791f4bf12f15fa0c2c53d27fbe515e5af3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="unix"></a>UNIX
プログラムを UNIX に移植する場合は、次のガイドラインに従ってください。  
  
-   SYS サブディレクトリからヘッダー ファイルを削除しないでください。 プログラムを UNIX に転送する予定がない場合にのみ、SYS ヘッダー ファイルを別の場所に配置することができます。  
  
-   引数としてパスとファイル名を表す文字列を実行するルーチンでは、UNIX と互換性のあるパス区切り記号を使用します。 UNIX は、この目的でスラッシュ (/) のみをサポートするのに対して、Win32 オペレーティング システムでは、円記号 (\\) とスラッシュ (/) の両方をサポートします。 そのため、このドキュメントでは、`#include` ステートメントなどのパス区切り記号として UNIX と互換性のあるスラッシュを使用します。 (ただし、Windows オペレーティング システム コマンド シェル (CMD.EXE) では、コマンド プロンプトで入力されたコマンドに含まれるスラッシュをサポートしません。)  
  
-   UNIX で正しく動作するパスとファイル名を使用します。UNIX では、大文字と小文字が区別されます。 Win32 オペレーティング システムのファイル アロケーション テーブル (FAT) ファイル システムでは、大文字と小文字が区別されません。NTFS ファイル システムでは、ディレクトリの一覧の大文字小文字を保持しますが、ファイル検索やその他のシステム操作での大文字小文字は無視します。  
  
    > [!NOTE]
    >  このバージョンの Visual C++ では、UNIX と互換性のある情報は、関数の説明から削除されています。  
  
## <a name="see-also"></a>参照  
 [互換性](../c-runtime-library/compatibility.md)