### Create Axios instance with javaScript class

```js
import axios from "axios";

export default class HttpRequest {
  instance;
  constructor(baseURL) {
    this.instance = axios.create({
      baseURL: baseURL,
    });
    this._initializeRequestInterceptor();
    this._initializeResponseInterceptor();
  }

  
  _initializeRequestInterceptor() {
    this.instance.interceptors.request.use(
      this._requestConfig,
      this._handleError
    );
  }


  _initializeResponseInterceptor() {
    this.instance.interceptors.response.use(
      this._handleResponse,
      this._handleError
    );
  }

  
  _requestConfig(config) {
    config.headers["Content-Type"] = "application/x-www-form-urlencoded";
    config.headers["crossOrigin"] = true;
    return config;
  }

  
  _handleResponse(response) {
    return response;
  }

  _handleError(error) {
    return Promise.reject(error);
  }
}

```

#Axios #create-axios-instance

```js
import HttpRequest from "./http-request";

export default class PostAPIRequest extends HttpRequest {
  constructor() {
    super("http://localhost:9000");
  }

  getPosts() {
    return this.instance.get("/posts");
  }
}
```