const assert = require('assert')
const url = require('url')
const rp = require('request-promise')

describe('object operations', () => {
  let data

  before(async () => {
    /**
     * INSTRUCTIONS:
     *
     * - Visit https://www.coindesk.com/api
     * - You will find "Historical BPI data" at the bottom of the page with instructions on composing the query
     * - Make a request for prices between January 1, 2019 - January 31, 2019
     * - Populate the params to complete the request (you don't have to use the `url` package)
     * - Attach the response to the data variable defined above
     */
    const params = {
      uri: url.format({/* TODO: */}),
      json: true
    }

    const {bpi} = await rp(params) || {}
    data = bpi
    // NOTE: you might find it useful to log the response here
  })

  it('should handle basic arithmetic', () => {
    /**
     * NOTE:
     *
     * The first test has been completed for demonstration.
     * It should pass if the query is acurate
     */
    const actual = Object.keys(data).reduce((sum, date) => sum + data[date], 0)
    const expected = 114390.02239999999
    assert.equal(actual, expected)
  })

  it('should create new object', () => {
    /**
     * INSTRUCTIONS:
     *
     * Extract only the results from Mondays
     * See expected result below
     */
    const actual = null // TODO:
    const expected = {
      '2019-01-01': 3869.47,
      '2019-01-08': 4029.9917,
      '2019-01-15': 3604.1333,
      '2019-01-22': 3598.2183,
      '2019-01-29': 3421.12
    }
    assert.deepEqual(actual, expected)
  })

  it('should handle finding', () => {
    /**
     * INSTRUCTIONS:
     *
     * Find the top value (Number) from any date
     * See expected result below
     */
    const actual = null // TODO:
    const expected = 4083.165
    assert.equal(actual, expected)
  })

  it('should handle sorting', () => {
    /**
     * INSTRUCTIONS:
     *
     * Return the top 5 dates in descending order
     * See expected result below
     */
    const actual = null // TODO:
    const expected = {
      '2019-01-06': 4083.165,
      '2019-01-07': 4041.4583,
      '2019-01-08': 4029.9917,
      '2019-01-09': 4028.2917,
      '2019-01-02': 3941.2167
    }
    assert.deepEqual(actual, expected)
  })
})