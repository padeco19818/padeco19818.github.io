export default function handler(req, res) {
  // 1. Only accept POST requests
  if (req.method !== 'POST') {
    return res.status(405).json({ error: 'Method not allowed' });
  }

  // 2. Log the incoming data (AdMob sends JSON)
  console.log('📨 AdMob Callback Received:', {
    timestamp: new Date().toISOString(),
    body: req.body,
    headers: req.headers
  });

  // 3. Example of what AdMob might send:
  // {
  //   "event": "consent_update",
  //   "userId": "user_12345",
  //   "consentStatus": "consented", // or "not_consented"
  //   "appId": "ca-app-pub-4865776169330826~4098899162",
  //   "platform": "android"
  // }

  // 4. IMPORTANT: Always return 200 OK immediately
  // Don't do heavy processing here
  res.status(200).json({ 
    status: 'success',
    message: 'Callback received' 
  });

  // 5. Optional: Process data further (async)
  // saveToDatabase(req.body); // Do this after sending response
}
