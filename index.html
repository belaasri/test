'use client'

import { useState } from 'react'
import { Button } from "@/components/ui/button"
import { Input } from "@/components/ui/input"
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card"
import { AlertCircle, Clock, Eye, Download } from 'lucide-react'

export default function YouTubeConverter() {
  const [url, setUrl] = useState('')
  const [videoData, setVideoData] = useState(null)
  const [error, setError] = useState('')
  const [loading, setLoading] = useState(false)
  const [downloading, setDownloading] = useState({ mp3: false, mp4: false })

  const handleSubmit = async (e) => {
    e.preventDefault()
    setLoading(true)
    setError('')
    setVideoData(null)

    const videoId = extractVideoId(url)
    if (!videoId) {
      setError('Invalid YouTube URL')
      setLoading(false)
      return
    }

    try {
      const response = await fetch(`https://youtube-v31.p.rapidapi.com/videos?part=contentDetails,snippet,statistics&id=${videoId}`, {
        method: 'GET',
        headers: {
          'x-rapidapi-host': 'youtube-v31.p.rapidapi.com',
          'x-rapidapi-key': 'd1c53133acmsh2e7c470c0bfbb2ep1a074cjsne9dd522da151'
        }
      })

      if (!response.ok) {
        throw new Error('Failed to fetch video data')
      }

      const data = await response.json()
      if (data.items && data.items.length > 0) {
        setVideoData(data.items[0])
      } else {
        setError('No video found')
      }
    } catch (err) {
      setError('An error occurred while fetching video data')
    } finally {
      setLoading(false)
    }
  }

  const extractVideoId = (url) => {
    const regExp = /^.*((youtu.be\/)|(v\/)|(\/u\/\w\/)|(embed\/)|(watch\?))\??v?=?([^#&?]*).*/
    const match = url.match(regExp)
    return (match && match[7].length === 11) ? match[7] : false
  }

  const handleDownload = async (format) => {
    setDownloading({ ...downloading, [format]: true })
    try {
      // In a real application, you would make an API call to your backend here
      // For this example, we'll simulate a download after a short delay
      await new Promise(resolve => setTimeout(resolve, 2000))
      console.log(`Downloading ${format} for video: ${videoData.id}`)
      // Simulated download completion
      const a = document.createElement('a')
      a.href = `https://example.com/download/${videoData.id}.${format}`
      a.download = `${videoData.snippet.title}.${format}`
      document.body.appendChild(a)
      a.click()
      document.body.removeChild(a)
    } catch (err) {
      setError(`Failed to download ${format.toUpperCase()}`)
    } finally {
      setDownloading({ ...downloading, [format]: false })
    }
  }

  const formatDuration = (duration) => {
    const match = duration.match(/PT(\d+H)?(\d+M)?(\d+S)?/)
    const hours = (match[1] ? match[1].slice(0, -1) : 0)
    const minutes = (match[2] ? match[2].slice(0, -1) : 0)
    const seconds = (match[3] ? match[3].slice(0, -1) : 0)
    return `${hours ? hours + ':' : ''}${minutes.padStart(2, '0')}:${seconds.padStart(2, '0')}`
  }

  const formatViews = (viewCount) => {
    return new Intl.NumberFormat('en-US', { notation: 'compact' }).format(viewCount)
  }

  return (
    <div className="container mx-auto p-4">
      <Card className="w-full max-w-2xl mx-auto">
        <CardHeader>
          <CardTitle className="text-2xl font-bold text-center">YouTube Converter</CardTitle>
        </CardHeader>
        <CardContent>
          <form onSubmit={handleSubmit} className="space-y-4">
            <Input
              type="url"
              placeholder="Paste YouTube link here"
              value={url}
              onChange={(e) => setUrl(e.target.value)}
              required
              aria-label="YouTube URL"
            />
            <Button type="submit" className="w-full" disabled={loading}>
              {loading ? 'Converting...' : 'Convert'}
            </Button>
          </form>

          {error && (
            <div className="flex items-center gap-2 mt-4 p-2 bg-red-100 text-red-700 rounded">
              <AlertCircle size={18} />
              <p>{error}</p>
            </div>
          )}

          {videoData && (
            <div className="mt-6 space-y-4">
              <h2 className="text-xl font-semibold">{videoData.snippet.title}</h2>
              <img
                src={videoData.snippet.thumbnails.medium.url}
                alt={videoData.snippet.title}
                className="w-full rounded-lg"
              />
              <div className="flex justify-between text-sm text-gray-600">
                <span className="flex items-center gap-1">
                  <Clock size={16} />
                  {formatDuration(videoData.contentDetails.duration)}
                </span>
                <span className="flex items-center gap-1">
                  <Eye size={16} />
                  {formatViews(videoData.statistics.viewCount)} views
                </span>
              </div>
              <div className="flex flex-col sm:flex-row gap-4">
                <Button 
                  onClick={() => handleDownload('mp3')} 
                  className="flex-1"
                  disabled={downloading.mp3}
                >
                  {downloading.mp3 ? 'Downloading...' : (
                    <>
                      <Download size={18} className="mr-2" />
                      Download MP3
                    </>
                  )}
                </Button>
                <Button 
                  onClick={() => handleDownload('mp4')} 
                  className="flex-1"
                  disabled={downloading.mp4}
                >
                  {downloading.mp4 ? 'Downloading...' : (
                    <>
                      <Download size={18} className="mr-2" />
                      Download MP4
                    </>
                  )}
                </Button>
              </div>
            </div>
          )}
        </CardContent>
      </Card>
    </div>
  )
}
