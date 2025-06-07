## 外部APIの呼び出しのミニレポート
### Q3-1. 郵便番号APIについて説明せよ。
* エンドポイントと機能
  エンドポイント：https://zipcloud.ibsnet.co.jp/api/search
  機能：リクエストされた郵便番号に対応した住所情報を表示する。
* リクエストとレスポンスのフォーマット
リクエスト例：https://zipcloud.ibsnet.co.jp/api/search?zipcode=7830060
zipcode= の後に自身の知りたい住所の郵便番号を入れることでリクエストできる。
レスポンス例：{
	"message": null,
	"results": [
		{
			"address1": "東京都",
			"address2": "台東区",
			"address3": "上野",
			"kana1": "ﾄｳｷｮｳﾄ",
			"kana2": "ﾀｲﾄｳｸ",
			"kana3": "ｳｴﾉ",
			"prefcode": "13",
			"zipcode": "1100005"
		}
	],
	"status": 200
}
今回使ったものを説明すると、resultsの中に住所についての情報が入っている。
その中のaddress1が都道府県を表しており、address2が市区町村を,address3が地名を表している。
statusは正常に処理が行われたか否かを表しており、200の場合は正常に行われたことを示している。
400の場合は入力パラメータエラー,500はAPI内部のエラーを表しており、エラーの場合はmessageの欄にエラー内容が表示されるようになっている。
### Q3-2. 各自で調査したAPIについて説明せよ。
* APIの名称と参照URL
  APIの名称：天気予報API（livedoor 天気互換）
  参照URL:https://weather.tsukumijima.net/
* エンドポイントと機能
  エンドポイント：https://weather.tsukumijima.net/api/forecast
  機能：リクエストされた地域に対応した天気情報を表示する。
* リクエストとレスポンスのフォーマット
　リクエスト例：https://weather.tsukumijima.net/api/forecast?city=400040
　city=の後ろに自身の知りたい地域のIDを入れることでリクエストできる。
  レスポンスのフォーマット例：
  {
    "publicTime": "2025-06-07T17:00:00+09:00",
    "publicTimeFormatted": "2025/06/07 17:00:00",
    "publishingOffice": "銚子地方気象台",
    "title": "千葉県 千葉 の天気",
    "link": "https://www.jma.go.jp/bosai/forecast/#area_type=offices&area_code=120000",
    "description": {
        "publicTime": "2025-06-07T16:34:00+09:00",
        "publicTimeFormatted": "2025/06/07 16:34:00",
        "headlineText": "",
        "bodyText": "　東日本は高気圧に覆われています。一方、前線が東シナ海から日本の南を通って日本の東にのびています。\n\n　千葉県は、曇りや晴れとなっています。\n\n　７日は、湿った空気の影響を受けるため、曇りとなるでしょう。\n\n　８日は、湿った空気の影響を受けるため、曇りとなる見込みです。\n\n　千葉県の太平洋沿岸の海上では、７日から８日にかけて、波がやや高いでしょう。",
        "text": "　東日本は高気圧に覆われています。一方、前線が東シナ海から日本の南を通って日本の東にのびています。\n\n　千葉県は、曇りや晴れとなっています。\n\n　７日は、湿った空気の影響を受けるため、曇りとなるでしょう。\n\n　８日は、湿った空気の影響を受けるため、曇りとなる見込みです。\n\n　千葉県の太平洋沿岸の海上では、７日から８日にかけて、波がやや高いでしょう。"
    },
    "forecasts": [
        {
            "date": "2025-06-08",
            "dateLabel": "今日",
            "telop": "曇り",
            "detail": {
                "weather": "くもり",
                "wind": "南の風　後　南西の風　海上　では　後　南西の風　やや強く",
                "wave": "０．５メートル　後　１メートル"
            },
            "temperature": {
                "min": {
                    "celsius": "20",
                    "fahrenheit": "68"
                },
                "max": {
                    "celsius": "27",
                    "fahrenheit": "80.6"
                }
            },
            "chanceOfRain": {
                "T00_06": "0%",
                "T06_12": "0%",
                "T12_18": "10%",
                "T18_24": "10%"
            },
            "image": {
                "title": "曇り",
                "url": "https://www.jma.go.jp/bosai/forecast/img/200.svg",
                "width": 80,
                "height": 60
            }
        },
        {
            "date": "2025-06-09",
            "dateLabel": "明日",
            "telop": "曇一時雨",
            "detail": {
                "weather": "くもり　一時　雨",
                "wind": "南の風　後　南東の風",
                "wave": "０．５メートル"
            },
            "temperature": {
                "min": {
                    "celsius": "19",
                    "fahrenheit": "66.2"
                },
                "max": {
                    "celsius": "23",
                    "fahrenheit": "73.4"
                }
            },
            "chanceOfRain": {
                "T00_06": "60%",
                "T06_12": "60%",
                "T12_18": "60%",
                "T18_24": "60%"
            },
            "image": {
                "title": "曇一時雨",
                "url": "https://www.jma.go.jp/bosai/forecast/img/202.svg",
                "width": 80,
                "height": 60
            }
        },
        {
            "date": "2025-06-10",
            "dateLabel": "明後日",
            "telop": "曇一時雨",
            "detail": {
                "weather": null,
                "wind": null,
                "wave": null
            },
            "temperature": {
                "min": {
                    "celsius": "18",
                    "fahrenheit": "64.4"
                },
                "max": {
                    "celsius": "22",
                    "fahrenheit": "71.6"
                }
            },
            "chanceOfRain": {
                "T00_06": "50%",
                "T06_12": "50%",
                "T12_18": "50%",
                "T18_24": "50%"
            },
            "image": {
                "title": "曇一時雨",
                "url": "https://www.jma.go.jp/bosai/forecast/img/202.svg",
                "width": 80,
                "height": 60
            }
        }
    ],
    "location": {
        "area": "関東",
        "prefecture": "千葉県",
        "district": "北西部",
        "city": "千葉"
    },
    "copyright": {
        "title": "(C) 天気予報 API（livedoor 天気互換）",
        "link": "https://weather.tsukumijima.net/",
        "image": {
            "title": "天気予報 API（livedoor 天気互換）",
            "link": "https://weather.tsukumijima.net/",
            "url": "https://weather.tsukumijima.net/logo.png",
            "width": 120,
            "height": 120
        },
        "provider": [
            {
                "link": "https://www.jma.go.jp/jma/",
                "name": "気象庁 Japan Meteorological Agency",
                "note": "気象庁 HP にて配信されている天気予報を JSON データへ編集しています。"
            }
        ]
    }
}
プロパティ数が多いため今回課題で使ったプロパティについて説明する。
location の中にcity（都市名）が入っており、forecasts の中に天気に関する情報が入っている。
date(日付),telop（天気）などが forecastsの中に入っている。
### Q3-3. 感想
* 今回の課題で苦労したこと
郵便番号のAPIでは動作確認時に、学校の住所を使ってしまったためエラー表示が出てしまい処理に不備があると勘違いしてしまった。その後、別の住所（上野や自宅の住所）で試したところ無事に動作が確認できた。
自分で調査したAPIでは、データ量が多いためプロパティなどのフォーマットを確認することに苦労した。
また、何を表示するべきかのデータの取捨選択に苦労した。
結局入力した場所の名前と、現在登録されている予報の日付とその天気を表示することにした。
* 演習を通して理解できたこと
APIのリクエスト文を確認すべきであるということと、APIのフォーマットの確認の重要性が理解できた。
* Web APIの利便性や課題など
APIによっては情報量が多くなるため、プロパティ量も増えて呼び出す処理を考えるときの負担も増えるように感じた。
