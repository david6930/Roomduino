pkj���Լ�д�ļ򵥿�
�������޶�/��תֵ��������

ethercard������ͷ�ʽ���Լ��Ĺ�

������£�
char website[] PROGMEM = "api.yeelink.net";
char urlBuf0[] PROGMEM = "/v1.0/device/xxx/sensor/xxx/";
char apiKey[] PROGMEM = "U-ApiKey: xxx";

static void my_result_cb (byte status, word off, word len)
{
  sscanf((char *)strstr((const char *)Ethernet::buffer + off, "\"value\""), "\"value\":%d", &yee[yeenum-1]);    //�ɼ��ؼ�������
}


          ether.browseUrl(urlBuf, "datapoints", website, apiKey, my_result_cb);   //�ɼ��ڵ�

          ether.httpPost (urlBuf, "datapoints", website, apiKey, "{\"value\":0}", my_result_cb);    //�ѽڵ��Ƶ���
